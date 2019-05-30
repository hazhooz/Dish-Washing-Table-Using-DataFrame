# Dish-Washing-Table-Using-DataFrame

#A simple program to generate a table of 30 rows that can be used in everyday life. 
#The program can be further optimized. 

import pandas as pd
import numpy as np


#Index represents date.
#Use date_range to generate 30 dates using the "periods" attribute starting from 2019-05-30.
#We'll use "index" for the dataframe creation.


index = pd.date_range('20190530', periods = 30)

#The period is 3. Adham's turn is first, then Ahmad's and at last Anas's.
#expand each value list to 30. Multiply each by 10.


turns = {'Adham': ['True','False','False']*10, 'Ahmad': ['False','True','False']*10, 'Anas': ['False','False','True']*10}

#Create a data frame.
#Use turns as data.


table = pd.DataFrame(turns, index = index)


#Write the data to a text file.


with open('filename', 'w') as fn:

	# "write" takes a string as a parameter. Use "to_string()" method to convert DataFrame object to string.


	fn.write(table.to_string())

	
