# 🐹 Python Challenge: Whack-a-Mole

**Level:** Beginner  
**Estimated time:** 40–60 minutes  
**Requirements:** Python, lists, `while`, `if` / `else`, `input()`  
**New tool:** The built-in `random` module

## 🎯 Your mission

Build a **Whack-a-Mole game in the terminal**! A mole 🐹 appears in one of nine holes, and the player must guess which hole it occupies. A successful hit earns one point. The game lasts **10 rounds**.

Your program should change the board every round, keep score, and show the final result.

## 🎮 Example gameplay

```text
====================
    WHACK-A-MOLE
====================
Round 1 / 10     Score: 0

🕳️ 🕳️ 🕳️
🕳️ 🐹 🕳️
🕳️ 🕳️ 🕳️

Choose a hole (1–9): 5
HIT! 🎯

Round 2 / 10     Score: 1

🕳️ 🕳️ 🐹
🕳️ 🕳️ 🕳️
🕳️ 🕳️ 🕳️

Choose a hole (1–9): 6
MISS! ❌

...

====================
     GAME OVER
====================
Final score: 7 / 10
Good job!
```

Hole numbers correspond to these positions:

```text
1 2 3
4 5 6
7 8 9
```

> **Important:** Python list indexes start at `0`, but players choose holes numbered from `1` to `9`.

## 🧩 Step-by-step instructions

### Step 1 — Create the board

Create a list called `board` with **9 empty holes**. Use the 🕳️ emoji for empty holes.

You can start with:

```python
board = ["🕳️"] * 9
```

Print its elements as **three rows of three holes** using list indexing.

Expected output:

```text
🕳️ 🕳️ 🕳️
🕳️ 🕳️ 🕳️
🕳️ 🕳️ 🕳️
```

**Checkpoint:** Can you explain what `board[0]` and `board[8]` represent?

### Step 2 — Place a mole randomly

1. Import the `random` module.
2. Generate a random position from `0` to `8`.
3. Replace the item at that position in `board` with `"🐹"`.
4. Print the updated board.

**Hint:** `random.randint(0, 8)` returns a random integer, including both ends.

**Checkpoint:** Run the program several times. Does the mole appear in different holes?

### Step 3 — Let the player choose a hole

1. Ask the player to enter a hole number from **1 to 9** using `input()`.
2. Convert the input to an integer.
3. Convert the player's number into a list index.
4. Compare that index with the mole's position.
5. Print `HIT!` if the player chose correctly, or `MISS!` otherwise.

**Checkpoint:** Does choosing `5` correctly target the center hole (`board[4]`)?

### Step 4 — Track the score

1. Create a variable called `score` and set it to `0`.
2. Increase the score by **1** for each successful hit.
3. Do not increase it for a miss.
4. Display the current score after each attempt.

### Step 5 — Add a game loop

The game should last **10 rounds**.

1. Create `round_number`, starting at `1`.
2. Use a `while` loop to repeat until all ten rounds have been played.
3. During each round:
   - Reset all nine holes to empty.
   - Choose a new random mole position.
   - Show the board and current round.
   - Ask for the player's choice.
   - Check the hit or miss and update the score.
   - Move to the next round.

**Checkpoint:** At the start of each new round, there should be **exactly one mole** on the board.

### Step 6 — Handle incorrect input

The player might type `0`, `12`, `hello`, or press Enter without typing anything.

Make the program accept **only whole numbers from 1 to 9**. When the input is invalid, show a helpful error and ask again **without using up a round**.

**Hint:** Try a second `while` loop and the string method `.isdigit()` before converting text to an integer.

### Step 7 — Display the final result

After round 10, print the final score out of 10, along with a message:

| Final score | Message |
|---|---|
| 0–3 | Keep practicing! |
| 4–7 | Good job! |
| 8–10 | Mole Master! |

## 🚀 Bonus challenges (optional)

Choose one or more once your basic game works.

- [ ] **Hit history:** Store all hits and misses in a list and print the history after the game.
- [ ] **Moving mole:** Change the mole's position after a missed attempt.
- [ ] **Multiple moles:** Place 2–3 moles on the board and store their positions in a list.
- [ ] **Limited lives:** The player starts with three lives; a miss costs one life, and zero lives ends the game.
- [ ] **High scores:** Let the player start another game, save each final score in a list, and display the highest score.

## ✅ Submission checklist

Before submitting, make sure:

- [ ] The board uses a **Python list** with 9 elements.
- [ ] The board displays as a **3 × 3 grid**.
- [ ] Exactly one mole appears in a random hole each round.
- [ ] Players choose holes **1–9**.
- [ ] The program correctly distinguishes hits from misses.
- [ ] The score updates correctly.
- [ ] A **`while` loop** runs the game for 10 rounds.
- [ ] Incorrect input does not crash the game or consume a round.
- [ ] The final score and result message appear at the end.

## 💡 Questions to think about

1. Why is a list useful for storing the game board?
2. What's the difference between a hole number and a list index?
3. What happens if you forget to reset the board at the start of a round?
4. Which condition makes your `while` loop stop?
5. How would you store the results of several rounds in another list?

**Deliverable:** Submit your `.py` file. Be ready to run the game and explain how your list changes from one round to the next.

**Challenge:** Make the game your own—add personality, creative messages, or a new mechanic!
