---
title: "Joshua Klotzkin - Games"
layout: textlay
excerpt: "Joshua Klotzkin: Game Search"
sitemap: false
permalink: /game_search
---


<html lang="en">
<body>
    <div id="root"></div>
    
    <script type="text/babel">
        // Paste the entire React component code from the artifact here
        const { useState } = React;
        const { Search, Trash2, Sparkles, Gamepad2 } = lucide;
        
        import React, { useState } from 'react';
import { Search, Trash2, Sparkles, Gamepad2 } from 'lucide-react';

const GameRecommendations = () => {
  const [inputGames, setInputGames] = useState(['', '', '', '', '']);
  const [recommendations, setRecommendations] = useState([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  const handleGameInput = (index, value) => {
    const newGames = [...inputGames];
    newGames[index] = value;
    setInputGames(newGames);
  };

  const clearInput = (index) => {
    const newGames = [...inputGames];
    newGames[index] = '';
    setInputGames(newGames);
  };

  const fetchRecommendations = async () => {
    const filledGames = inputGames.filter(game => game.trim() !== '');
    
    if (filledGames.length === 0) {
      setError("Please enter at least one game to get recommendations.");
      return;
    }

    setLoading(true);
    setError(null);

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
              content: `Based on these games the user enjoys: ${filledGames.join(', ')}

Please analyze the genres, themes, and game modes of these games and recommend 10 similar games from IGDB that they would likely enjoy. 

For each recommendation, provide:
- name: The game title
- rating: IGDB rating (out of 100)
- release_year: Year released
- genres: Array of genre names
- themes: Array of theme names
- game_modes: Array of game mode names (e.g., "Single player", "Multiplayer", "Co-op")
- summary: Brief description
- similarity_reason: Why this game matches their preferences (one sentence)

Return ONLY valid JSON with no preamble or markdown formatting. Use this exact structure:
[{"name": "Game Name", "rating": 85, "release_year": 2023, "genres": ["Action", "RPG"], "themes": ["Fantasy"], "game_modes": ["Single player"], "summary": "Description", "similarity_reason": "Reason"}]`
            }
          ],
        })
      });

      const data = await response.json();
      const text = data.content.find(item => item.type === "text")?.text || "";
      const cleanText = text.replace(/```json|```/g, "").trim();
      const parsedGames = JSON.parse(cleanText);
      setRecommendations(parsedGames);
    } catch (err) {
      setError("Failed to fetch recommendations. Please try again.");
      console.error(err);
    } finally {
      setLoading(false);
    }
  };

  return (
    <div className="min-h-screen bg-gradient-to-br from-indigo-900 via-purple-900 to-pink-900 p-6">
      <div className="max-w-6xl mx-auto">
        <div className="text-center mb-12">
          <h1 className="text-5xl font-bold text-white mb-4 flex items-center justify-center gap-3">
            <Sparkles className="w-12 h-12" />
            Game Recommendations
          </h1>
          <p className="text-gray-200 text-lg">Enter 5 games you love, and we'll find 10 more you'll enjoy!</p>
        </div>

        {/* Input Section */}
        <div className="bg-white/10 backdrop-blur-md rounded-2xl p-8 mb-8 shadow-2xl border border-white/20">
          <h2 className="text-2xl font-bold text-white mb-6 flex items-center gap-2">
            <Gamepad2 className="w-6 h-6" />
            Your Favorite Games
          </h2>
          
          <div className="space-y-4 mb-6">
            {inputGames.map((game, index) => (
              <div key={index} className="flex gap-2">
                <div className="flex-shrink-0 w-8 h-12 bg-purple-500 rounded-lg flex items-center justify-center font-bold text-white">
                  {index + 1}
                </div>
                <input
                  type="text"
                  value={game}
                  onChange={(e) => handleGameInput(index, e.target.value)}
                  placeholder={`Game ${index + 1}`}
                  className="flex-1 px-4 py-3 bg-white/20 border-2 border-white/30 rounded-lg text-white placeholder-gray-300 focus:outline-none focus:border-purple-400 focus:bg-white/30 transition-all"
                />
                {game && (
                  <button
                    onClick={() => clearInput(index)}
                    className="flex-shrink-0 w-12 h-12 bg-red-500 hover:bg-red-600 rounded-lg flex items-center justify-center transition-colors"
                  >
                    <Trash2 className="w-5 h-5 text-white" />
                  </button>
                )}
              </div>
            ))}
          </div>

          <button
            onClick={fetchRecommendations}
            disabled={loading}
            className="w-full bg-gradient-to-r from-purple-500 to-pink-500 hover:from-purple-600 hover:to-pink-600 disabled:from-gray-500 disabled:to-gray-600 text-white font-bold py-4 px-6 rounded-lg transform transition-all hover:scale-105 active:scale-95 shadow-lg flex items-center justify-center gap-2"
          >
            <Search className="w-5 h-5" />
            {loading ? 'Finding Games...' : 'Get Recommendations'}
          </button>
        </div>

        {/* Loading State */}
        {loading && (
          <div className="text-center py-12">
            <div className="inline-block animate-spin rounded-full h-16 w-16 border-4 border-purple-400 border-t-transparent"></div>
            <p className="text-white mt-4 text-lg">Analyzing your preferences...</p>
          </div>
        )}

        {/* Error State */}
        {error && (
          <div className="bg-red-500/20 border-2 border-red-400 rounded-lg p-6 text-center mb-8">
            <p className="text-red-200 text-lg">{error}</p>
          </div>
        )}

        {/* Recommendations */}
        {!loading && recommendations.length > 0 && (
          <div>
            <h2 className="text-3xl font-bold text-white mb-6 text-center">
              Recommended For You
            </h2>
            <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
              {recommendations.map((game, index) => (
                <div
                  key={index}
                  className="bg-white/10 backdrop-blur-md rounded-xl p-6 hover:bg-white/20 transition-all hover:transform hover:scale-105 shadow-xl border border-white/20"
                >
                  <div className="flex items-start justify-between mb-3">
                    <h3 className="text-xl font-bold text-white flex-1 pr-2">
                      {game.name}
                    </h3>
                    {game.rating && (
                      <div className="bg-yellow-500 px-3 py-1 rounded-full">
                        <span className="text-white font-bold text-sm">
                          {Math.round(game.rating)}
                        </span>
                      </div>
                    )}
                  </div>
                  
                  {game.release_year && (
                    <p className="text-gray-300 text-sm mb-3">
                      Released: {game.release_year}
                    </p>
                  )}

                  <div className="flex flex-wrap gap-2 mb-3">
                    {game.genres && game.genres.map((genre, i) => (
                      <span key={i} className="bg-blue-500 px-2 py-1 rounded text-white text-xs font-semibold">
                        {genre}
                      </span>
                    ))}
                    {game.themes && game.themes.map((theme, i) => (
                      <span key={i} className="bg-purple-500 px-2 py-1 rounded text-white text-xs font-semibold">
                        {theme}
                      </span>
                    ))}
                    {game.game_modes && game.game_modes.map((mode, i) => (
                      <span key={i} className="bg-green-500 px-2 py-1 rounded text-white text-xs font-semibold">
                        {mode}
                      </span>
                    ))}
                  </div>
                  
                  {game.summary && (
                    <p className="text-gray-300 text-sm mb-3">
                      {game.summary}
                    </p>
                  )}

                  {game.similarity_reason && (
                    <div className="bg-pink-500/30 border border-pink-400/50 rounded-lg p-3 mt-3">
                      <p className="text-pink-100 text-sm italic">
                        <strong>Why you'll like it:</strong> {game.similarity_reason}
                      </p>
                    </div>
                  )}
                </div>
              ))}
            </div>
          </div>
        )}
      </div>
    </div>
  );
};

export default GameRecommendations;
        
        ReactDOM.render(<GameRecommendations />, document.getElementById('root'));
    </script>
    
    <script src="https://unpkg.com/lucide@latest"></script>
</body>
</html>
