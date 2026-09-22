# Assingment-3_Llerena

This is code for analyzing the “NBA_Player_Stats.tsv" file using the NumPy library. Formulas such as (Made / Attempted) * 100 were used to calculate the players' accuracy based on the table. To display the player and their season on the screen, the two columns are assigned to the “player-season” variable. They are then stacked using .column_stack().

Categories to calculate: field goal accuracy, three point accuracy, free throw accuracy, average points scored per game, overall shooting accuracy, average blocks per game, and average steals per game. 

First, the file is opened as an np.array with dtype=str using genfromtxt(). Then, each relevant column is assigned to a float variable to perform the calculations. Players and Season are saved on a variable called 'players_season'. In order, to avoid negative values caused by human error, `np.where` is used to filter out values less than 0. As mentioned earlier, the information is printed using `np.column_stack()`. Here’s an example: `print(np.column_stack((players_season, field_arr)))`


Finally, I wanted to explain how the top 100 players in each “category” were calculated. First, the indices were determined using `np.argsort()` by passing it the array containing all the data for that category (at first, I considered sorting the bottom 100 since it’s in ascending order, but you get the same result by reversing the order and sorting the top 100). The indices are stored in a variable ending in “idx” (which varies by category); then, those indices are passed to “player_season” to identify the names corresponding to the top 100 along with the season—the resulting variable ends in “players.” Next, the indices are passed to the array containing all the data for the category to retrieve the values. Finally, using `np.column_stack` again, the columns—name, season, and value—are grouped together. Here’s an example:

#Top Field Goal Accuracy

fieldG_idx = np.argsort(-field_arr)[:100]

fieldG_players = players_season[fieldG_idx]

fieldG_values = field_arr[fieldG_idx]



top_fieldG  = np.column_stack((fieldG_players, fieldG_values))
