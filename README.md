![Vowle](https://raw.githubusercontent.com/gazj/vowle/main/public/img/banner.png)
<div align="center">
  <img src="https://github.com/gazj/vowle/workflows/Publish/badge.svg?branch=main" alt="Publish workflow"/>
</div>

---
A recreation of the popular game [Wordle](https://www.nytimes.com/games/wordle/) by Josh Wardle (now purchased by the New York Times), with additional modes and features.

# Additional Features
- Words are chosen from the list of words at random instead of in sequence, and the solution is not stored in localStorage, making it harder to cheat. The seed for the random number is created from the date, ensuring that everyone gets the same random number, so people can still compare answers.
- When you complete a game the definition of the word is shown on the end of game modal.
- In addition to the other statistics, your average guesses and your losses are also displayed on the win modal.
- When the timer reaches 0 for a given game mode it changes into a refresh button instead of just staying at 00:00:00.
- When the timer reaches 0 for a given game mode a refresh button appears in the top left corner.
- A tips widget in the settings menu with useful information about the functionality of the game.
- Right clicking a submitted word on the board will tell you its definition.
- Right clicking a submitted word on the board will tell you how many possible words could have been played there, taking all previous information into account.
- Right clicking the row below the last submitted word will tell you how many possibilities there are taking all previous information into account.
- The game mode is reflected in the url, allowing you to share a game mode directly.
- You can share a link to a specific game number, allowing you to play historical games, and share specific rounds of the faster changing modes with your friends.
- You can access previous games from the settings menu by inputting a game number or link.
- Service worker which allows the game to be easily downloaded as a progressive web app and run offline.
- Give Up button.
- Vowel and consonant positions are shown above the game board.

## Additional modes
The game mode can be changed from the settings menu.

**Hourly mode**: A new word every hour.

**Infinite mode**: A new word every time you refresh, for the true addicts.

# Forking this project
Anybody is welcome to fork this repository and do what they like with it, provided they follow the accompanying license (GPL-3.0).
