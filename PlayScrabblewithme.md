# LET'S PLAY A GAME OF SCRABBLE

What is Scrabble?

![image](https://user-images.githubusercontent.com/79688274/131106883-ab0559e4-532c-4e8e-90e5-49f8dd7589ff.png)


Scrabble is board-and-tile game in which two to four players compete in forming words with lettered tiles on a 225-square board; words spelled out by letters on the tiles interlock like words in a crossword puzzle. (took this description from the internet HAHAH but if you're interested, do check it out on your own!)

Today, we will be processing some data from my family playing scrabble. We will use dictionaries to organize players, words, and points. Ready to play with some data? LETS GO!!!

### Before we begin, we must know how many points each letter is worth. I have prepared two lists that contains the letters and the points


```python
letters = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z", " "]
points = [1, 3, 3, 2, 1, 4, 2, 4, 1, 8, 5, 1, 3, 4, 1, 3, 10, 1, 1, 1, 1, 4, 4, 8, 4, 10, 0]

# We would like to combine these two into a dictionary that would map a letter to its point value.
# This can be done by using a LIST COMPREHENSION and ZIP.

letters_to_points = {letters : points for letters , points in zip(letters,points)}
print(letters_to_points)
```

    {'A': 1, 'B': 3, 'C': 3, 'D': 2, 'E': 1, 'F': 4, 'G': 2, 'H': 4, 'I': 1, 'J': 8, 'K': 5, 'L': 1, 'M': 3, 'N': 4, 'O': 1, 'P': 3, 'Q': 10, 'R': 1, 'S': 1, 'T': 1, 'U': 1, 'V': 4, 'W': 4, 'X': 8, 'Y': 4, 'Z': 10, ' ': 0}


There we go! Now, we know how many points each letter of the alphabet is worth in this fun game of Scrabble!

### Part 1 : We will want to create a function that will take in a word and return how many points that word is worth. Let's see how this goes!


```python
# Step 1 : We created a function called score_word():
def score_word(word):
    # Step 2 : We will create a variable called point_total and set it to 0 so that we can accumlate the points here
  point_total = 0
# Step 3 : We will iterate through the letters of each word using for loops. We use word.upper() so that ever letter we use will be capitalized
  for letter in word.upper():
    # Step 4 : We use the .get() dictionary function to select the "letter" and then add it into point_total
    point_total += letters_to_points.get(letter, 0)
    # Step 5 : Return point_total
  return point_total
```

With our function in place, let's try it out! Hmmmmmmm... I want to check how many points "Beautiful" is worth.


```python
beautiful_score = score_word("beautiful")
print(beautiful_score)
```

    14


By using this function, we can tell that "Beautiful" is worth 14 points! YAY OUR FUNCTION WORKS!!!

### Part 2 : Calculating the Total Score of the game for each player in the family

Ready? LETS GO!


```python
# I have stored the words that each player has come up with in the dictionary below! 

player_to_words = {
  "Bryan" : ["BLAME", "TABLETENNIS", "ENDGAME"],
  "Rayshon" : ["EARTH", "SATURN", "MERCURY"],
  "Lizanne" : ["ERASER", "STOMACH", "RETRIEVER"],
  "Garrett" : ["ZAPDOS", "COMATOSE", "PERIODICALLY"],
  "Carolyn" : ["XENON", "FIGHTER", "AMAZON"]
}
```


```python
# Step 1 : Create an empty dictionary to store future data
player_to_points = {}

# Step 2 : We will need to use the FOR loop to iterate through the keys and values. Utilizing .items() will help us
for player, words in player_to_words.items():
    # Step 3 : Create a variable called player_points and assign it to 0. This will be where we accumulate our points.
    player_points = 0
    # Step 4 : We will use FOR loop again to iterate through the list to get each individual word 
    for word in words:
        # Step 5 : Remember the score_word() function from part 1? Yeap, we'll be using it here to get the points
        player_points += score_word(word)
        # Step 7 : Add the new data into the player_to_points dictionary 
        player_to_points[player] = player_points
# Step 7 : Print it out! 
print(player_to_points)
```

    {'Bryan': 42, 'Rayshon': 31, 'Lizanne': 32, 'Garrett': 50, 'Carolyn': 52}


There we have it! We can tell from the past three rounds, Carolyn is currently taking the lead with a whopping 52 points. AMAZING!!! 

Saw this online and I thought that it was very creative to use Python to calculate the number of points each person has accumulated for each word that they have! I had fun doing this and if you're looking to calculate Scrabble points using Python, I hope that this will be helpful!

Alrighty, stay safe and happy coding!
