# Assingment-3_Llerena

This is code for analyzing the “NBA_Player_Stats.tsv" file using the NumPy library. Formulas such as (Made / Attempted) * 100 were used to calculate the players' accuracy based on the table. To display the player and their season on the screen, the two columns are assigned to the “player-season” variable. They are then stacked using .column_stack().


First, the file is opened as an np.array with dtype=str using genfromtxt(). Then, each relevant column is assigned to a float variable to perform the calculations. To avoid negative values caused by human error, `np.where` is used to filter out values less than 0. As mentioned earlier, the information is printed using `np.column_stack()`. Here’s an example: `print(np.column_stack((players_season, field_arr)))`
