---
title: "Joshua Klotzkin - Games"
layout: textlay
excerpt: "Joshua Klotzkin: Game Search"
sitemap: false
permalink: /game_search
---
import React, { useState } from 'react';
import { Search, Star, Calendar, Users } from 'lucide-react';

const GameSearch = () => {
  const [selectedGenre, setSelectedGenre] = useState(null);
  const [games, setGames] = useState([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  // Common IGDB genre IDs
  const genres = [
    { id: 4, name: 'Fighting', color: 'bg-red-500' },
    { id: 5, name: 'Shooter', color: 'bg-orange-500' },
    { id: 7, name: 'Music', color: 'bg-purple-500' },
    { id: 8, name: 'Platform', color: 'bg-blue-500' },
    { id: 9, name: 'Puzzle', color: 'bg-green-500' },
    { id: 10, name: 'Racing', color: 'bg-yellow-500' },
    { id: 12, name: 'RPG', color: 'bg-indigo-500' },
    { id: 13, name: 'Simulator', color: 'bg-teal-500' },
    { id: 14, name: 'Sport', color: 'bg-lime-500' },
    { id: 15, name: 'Strategy', color: 'bg-cyan-500' },
    { id: 31, name: 'Adventure', color: 'bg-amber-500' },
    { id: 33, name: 'Arcade', color: 'bg-rose-500' }
  ];

  const fetchGames = async (genreId, genreName) => {
    setLoading(true);
    setError(null);
    setSelectedGenre(genreName);

    try {
      const response = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 4000,
          messages: [
            {
              role: "user",
              content: `Please provide a JSON array of the top 20 ${genreName} games from IGDB. For each game include: name, rating (out of 100), release_year, and a brief summary. Return ONLY valid JSON with no preamble or markdown formatting. Use this exact structure:
[{"name": "Game Name", "rating": 95, "release_year": 2023, "summary": "Brief description"}]`
            }
          ],
        })
      });

      const data = await response.json();
      const text = data.content.find(item => item.type === "text")?.text || "";
      const cleanText = text.replace(/```json|```/g, "").trim();
      const parsedGames = JSON.parse(cleanText);
      setGames(parsedGames);
    } catch (err) {
      setError("Failed to fetch games. Please try again.");
      console.error(err);
    } finally {
      setLoading(false);
    }
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900 p-6">
      <div className="max-w-7xl mx-auto">
        <div className="text-center mb-12">
          <h1 className="text-5xl font-bold text-white mb-4 flex items-center justify-center gap-3">
            <Search className="w-12 h-12" />
            Game Search
          </h1>
          <p className="text-gray-300 text-lg">Discover top games by genre from IGDB</p>
        </div>

        {/* Genre Buttons */}
        <div className="mb-12">
          <h2 className="text-2xl font-semibold text-white mb-6 text-center">Select a Genre</h2>
          <div className="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
            {genres.map((genre) => (
              <button
                key={genre.id}
                onClick={() => fetchGames(genre.id, genre.name)}
                className={`${genre.color} hover:opacity-90 text-white font-semibold py-4 px-6 rounded-lg transform transition-all hover:scale-105 active:scale-95 shadow-lg ${
                  selectedGenre === genre.name ? 'ring-4 ring-white' : ''
                }`}
              >
                {genre.name}
              </button>
            ))}
          </div>
        </div>

        {/* Loading State */}
        {loading && (
          <div className="text-center py-12">
            <div className="inline-block animate-spin rounded-full h-16 w-16 border-4 border-purple-500 border-t-transparent"></div>
            <p className="text-white mt-4 text-lg">Loading {selectedGenre} games...</p>
          </div>
        )}

        {/* Error State */}
        {error && (
          <div className="bg-red-500/20 border-2 border-red-500 rounded-lg p-6 text-center">
            <p className="text-red-200 text-lg">{error}</p>
          </div>
        )}

        {/* Games Grid */}
        {!loading && games.length > 0 && (
          <div>
            <h2 className="text-3xl font-bold text-white mb-6 text-center">
              Top {selectedGenre} Games
            </h2>
            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
              {games.map((game, index) => (
                <div
                  key={index}
                  className="bg-white/10 backdrop-blur-md rounded-xl p-6 hover:bg-white/20 transition-all hover:transform hover:scale-105 shadow-xl border border-white/20"
                >
                  <div className="flex items-start justify-between mb-3">
                    <h3 className="text-xl font-bold text-white flex-1 pr-2">
                      {game.name}
                    </h3>
                    {game.rating && (
                      <div className="flex items-center gap-1 bg-yellow-500 px-2 py-1 rounded-full">
                        <Star className="w-4 h-4 text-white fill-white" />
                        <span className="text-white font-semibold text-sm">
                          {Math.round(game.rating)}
                        </span>
                      </div>
                    )}
                  </div>
                  
                  {game.release_year && (
                    <div className="flex items-center gap-2 text-gray-300 mb-3">
                      <Calendar className="w-4 h-4" />
                      <span>{game.release_year}</span>
                    </div>
                  )}
                  
                  {game.summary && (
                    <p className="text-gray-300 text-sm line-clamp-3">
                      {game.summary}
                    </p>
                  )}
                </div>
              ))}
            </div>
          </div>
        )}

        {/* Initial State */}
        {!loading && !error && games.length === 0 && (
          <div className="text-center py-12">
            <Users className="w-24 h-24 text-purple-400 mx-auto mb-4 opacity-50" />
            <p className="text-gray-400 text-xl">Select a genre to discover amazing games!</p>
          </div>
        )}
      </div>
    </div>
  );
};

export default GameSearch;
