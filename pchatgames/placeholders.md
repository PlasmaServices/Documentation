# Placeholders

### Game Status Placeholders

* `%pchatgames_game_active%` - Returns "true" or "false"
* `%pchatgames_game_status%` - Returns "Active" or "Inactive"
* `%pchatgames_current_question%` - Current game question or "No active game"
* `%pchatgames_current_answer%` - Current answer (only visible to ops/admins) or "Hidden"
* `%pchatgames_current_game_type%` - Type of current game or "None"

### Timing Placeholders

* `%pchatgames_time_elapsed%` - Time elapsed since game started (e.g., "12.5s")
* `%pchatgames_time_remaining%` - Time remaining before timeout (e.g., "32.5s")
* `%pchatgames_countdown%` - Simple countdown in whole seconds (e.g., "32")
* `%pchatgames_time_progress_bar%` - Visual progress bar showing time elapsed

### Configuration Placeholders

* `%pchatgames_auto_start_enabled%` - "Enabled" or "Disabled"
* `%pchatgames_auto_start_interval%` - Auto-start interval in minutes
* `%pchatgames_timeout_seconds%` - Game timeout duration
* `%pchatgames_case_sensitive%` - "Yes" or "No"

### Game Type Status

* `%pchatgames_math_enabled%` - "Enabled" or "Disabled"
* `%pchatgames_spell_enabled%` - "Enabled" or "Disabled"
* `%pchatgames_unscramble_enabled%` - "Enabled" or "Disabled"
* `%pchatgames_trivia_enabled%` - "Enabled" or "Disabled"
* `%pchatgames_enabled_games_count%` - Number of enabled game types

### Math Game Settings

* `%pchatgames_math_min_first%` - Minimum value for first number
* `%pchatgames_math_max_first%` - Maximum value for first number
* `%pchatgames_math_min_second%` - Minimum value for second number
* `%pchatgames_math_max_second%` - Maximum value for second number

### Word/Question Counts

* `%pchatgames_spell_words_count%` - Number of spell words configured
* `%pchatgames_unscramble_words_count%` - Number of unscramble words configured
* `%pchatgames_trivia_questions_count%` - Number of trivia questions configured

### Reward Information

* `%pchatgames_money_rewards_enabled%` - "Enabled" or "Disabled"
* `%pchatgames_money_reward_min%` - Minimum money reward
* `%pchatgames_money_reward_max%` - Maximum money reward
* `%pchatgames_money_reward_fixed%` - Fixed money reward amount
* `%pchatgames_money_reward_random%` - "Random" or "Fixed"
* `%pchatgames_command_rewards_enabled%` - "Enabled" or "Disabled"
* `%pchatgames_item_rewards_enabled%` - "Enabled" or "Disabled"

### Player Statistics

* `%pchatgames_player_wins%` - Player's total wins
* `%pchatgames_player_games_played%` - Player's total games participated
* `%pchatgames_player_win_rate%` - Player's win percentage
* `%pchatgames_player_average_time%` - Player's average response time
* `%pchatgames_player_best_time%` - Player's fastest response time
* `%pchatgames_player_current_streak%` - Player's current win streak
* `%pchatgames_player_best_streak%` - Player's best win streak
* `%pchatgames_player_total_money_won%` - Total money won by player
* `%pchatgames_player_favorite_game%` - Player's most played game type
* `%pchatgames_player_last_win%` - When player last won

### Game-Specific Player Stats

* `%pchatgames_player_wins_MATH%` - Player's wins in math games
* `%pchatgames_player_wins_SPELL%` - Player's wins in spell games
* `%pchatgames_player_wins_UNSCRAMBLE%` - Player's wins in unscramble games
* `%pchatgames_player_wins_TRIVIA%` - Player's wins in trivia games
* `%pchatgames_player_played_MATH%` - Player's math games played
* `%pchatgames_player_played_SPELL%` - Player's spell games played
* `%pchatgames_player_played_UNSCRAMBLE%` - Player's unscramble games played
* `%pchatgames_player_played_TRIVIA%` - Player's trivia games played
* `%pchatgames_player_winrate_MATH%` - Player's math win rate
* `%pchatgames_player_winrate_SPELL%` - Player's spell win rate
* `%pchatgames_player_winrate_UNSCRAMBLE%` - Player's unscramble win rate
* `%pchatgames_player_winrate_TRIVIA%` - Player's trivia win rate

### Server Statistics

* `%pchatgames_total_games_played%` - Total games played on server
* `%pchatgames_total_wins%` - Total wins on server
* `%pchatgames_total_players%` - Number of players with statistics
* `%pchatgames_most_popular_game%` - Most played game type
* `%pchatgames_top_player%` - Player with most wins
* `%pchatgames_fastest_time_ever%` - Fastest response time ever
* `%pchatgames_fastest_time_player%` - Player who holds the fastest time record

### Leaderboard Placeholders

* `%pchatgames_top_1_wins%` - Top player's win count (1st place)
* `%pchatgames_top_1_wins_name%` - Top player's name (1st place)
* `%pchatgames_top_2_wins%` - 2nd place player's win count
* `%pchatgames_top_2_wins_name%` - 2nd place player's name
* `%pchatgames_top_3_wins%` - 3rd place player's win count
* `%pchatgames_top_3_wins_name%` - 3rd place player's name
* ... (continues up to top\_10)
* `%pchatgames_top_1_winrate%` - Top player's win rate (1st place)
* `%pchatgames_top_1_winrate_name%` - Top win rate player's name (1st place)
* `%pchatgames_top_2_winrate%` - 2nd place player's win rate
* `%pchatgames_top_2_winrate_name%` - 2nd place player's name
* ... (continues up to top\_10)
