# Ex-01_DS_Data_Cleansing


## AIM
To read the given data and perform data cleaning and save the cleaned data to a file. 

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. 
Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information. 

# ALGORITHM
### STEP 1
Read the given Data
### STEP 2
Get the information about the data
### STEP 3
Remove the null values from the data
### STEP 4
Save the Clean data to the file


# CODE
```
import pandas as pd
df=pd.read_csv('Data_set.csv')
print("Checking For Null values:")
print(df.isnull().sum())
df['show_name']=df['show_name'].fillna(df['show_name'].mode()[0])
df['aired_on']=df['aired_on'].fillna(df['aired_on'].mode()[0])
df['original_network']=df['original_network'].fillna(df['original_network'].mode()[0])
df['rating']=df['rating'].fillna(df['rating'].mean())
df['current_overall_rank']=df['current_overall_rank'].fillna(df['current_overall_rank'].mean())
df['watchers']=df['watchers'].fillna(df['watchers'].mean())
print()
print("Cleansed data:")
print(df,"\n")
print("Checking for Null after cleansing data:")
print(df.isnull().sum())
#saving clean data to file 
df.to_csv('Data_set.csv', index=False)
```
# OUPUT
```
Checking For Null values:
show_name                   0
country                     0
num_episodes                0
aired_on                    0
original_network            0
rating                      0
current_overall_rank        0
lifetime_popularity_rank    0
watchers                    0
dtype: int64

Cleansed data:
                   show_name      country  num_episodes             aired_on  \
0           A Korean Odyssey  South Korea            16     Friday, Saturday   
1           A Korean Odyssey  South Korea            16     Friday, Saturday   
2     Descendants of the Sun  South Korea            16  Wednesday, Thursday   
3          Boys Over Flowers  South Korea            25      Monday, Tuesday   
4                          W  South Korea            16  Wednesday, Thursday   
..                       ...          ...           ...                  ...   
95  Shut Up: Flower Boy Band  South Korea            16      Monday, Tuesday   
96                     Blood  South Korea            20      Monday, Tuesday   
97        Chicago Typewriter  South Korea            16     Friday, Saturday   
98      Sungkyunkwan Scandal  South Korea            20      Monday, Tuesday   
99                  Vagabond  South Korea            16     Friday, Saturday   

   original_network  rating  current_overall_rank  lifetime_popularity_rank  \
0               tvN     8.9                  33.0                         1   
1              jTBC     8.7                  89.0                         2   
2              KBS2     8.7                  77.0                         3   
3              KBS2     7.7                2249.0                         4   
4               MBC     8.5                 201.0                         5   
..              ...     ...                   ...                       ...   
95              tvN     8.1                 806.0                        99   
96             KBS2     7.4                3271.0                       100   
97              tvN     8.8                  51.0                       101   
98             KBS2     8.2                 605.0                       102   
99     SBS, Netflix     8.5                 238.0                       103   

         watchers  
0   111706.000000  
1   100950.000000  
2    96318.000000  
3    94228.000000  
4    92121.000000  
..            ...  
95   34668.000000  
96   34666.000000  
97   52994.907216  
98   34615.000000  
99   34523.000000  

[100 rows x 9 columns] 

Checking for Null after cleansing data:
show_name                   0
country                     0
num_episodes                0
aired_on                    0
original_network            0
rating                      0
current_overall_rank        0
lifetime_popularity_rank    0
watchers                    0
dtype: int64
```