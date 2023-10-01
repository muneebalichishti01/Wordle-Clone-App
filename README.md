# Wordle Clone App

In this assignment, I created a Wordle game with HTML, CSS, and JavaScript
NOTE: This project was simple so was not deployed using Netlify, refer to SAMPLE below

---

Sample:
![Imgur](https://i.imgur.com/VmHP3up.png)

## 📝 Details

- Added HTML code to the [index.html](./wordle/index.html) file
- Added CSS code to the [style.css](./wordle/style.css) file
- Added JavaScript code to the [wordle.js](./wordle/wordle.js) file

---

## :page_with_curl: Notes
- The page reads a dictionary of words from this endpoint: `https://api.masoudkf.com/v1/wordle`. The endpoint requires an API key (`sw0Tr2othT1AyTQtNDUE06LqMckbTiKWaVYhuirv`). Used `fetch` and added the key like the following:
    ```js
    const res = await fetch("https://api.masoudkf.com/v1/wordle", {
        headers: {
        "x-api-key": "sw0Tr2othT1AyTQtNDUE06LqMckbTiKWaVYhuirv",
        },
    });
  ```
- Here's a sample response of what the endpoint returns. It returns a `JSON` object

    ```json
    {
    "statusCode": 200,
    "dictionary": [
        {
            "word": "Pain",
            "hint": "Attending any class other than ENSF 381 gives you ____"
        },
        {
            "word": "Nerd",
            "hint": "You may be considered one, if you like Star Trek"
        }
        ]
    }
    ```
- Unlike the original Wordle game, it does not check if the word exists in the dictionary
- The `Start Over` button becomes `disabled` while the code is getting the dictionary from the endpoint for the first time, and say `Loading...`
- Captures key events from the user and populate the boxes
- Users can use the `Backspace` key to remove characters from the word 
- Users must use the `Enter` key to submit an answer
- If a user hits the `Enter` key while the word is not complete, the page alerts the user to finish the word first
- After a word submission:
    - Letters in the right spot gets a green background
    - Letters in the word but in the wrong spot gets a yellowish background
    - Letters not in the word gets a gray background 
- At any time in the game, users can use the `?` icon on the menu to see a hint about the word. This hint is part of the dictionary returned from the endpoint
- When a user wins, the page shows a congratulation image
- When a user loses, they get a message with a red background saying they couldn't guess the word and lost
- The `i` icon in the menu shows the game instructions
- The Moon icon in the menu can toggle the page from Light to Dark theme
- Used vanilla JavaScript (JavaScript without any external libraries, such as React) for this project

