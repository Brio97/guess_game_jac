# 🎲 Number Guessing Game (Jac + ByLLM)

A fun **AI-powered number guessing game** built with [Jac language](https://jac-lang.org) and [ByLLM](https://pypi.org/project/byllm/).  
The game picks a random number between **1 and 10**, and an LLM (Gemini / GPT) provides **creative hints** to guide your guesses.

---

## 🚀 Features
- Uses **Jac walkers and nodes** to model the game flow.
- Integrates with **ByLLM** for AI-generated hints.
- Playable in **CLI mode** or as a **cloud API** with `jac serve`.

---

## 🛠️ Environment Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/Brio97/guess_game_jac.git
   cd Guess
Create and activate a virtual environment

bash
Copy code
python3 -m venv jac-env
source jac-env/bin/activate
Install dependencies

bash
Copy code
pip install jac byllm jac-cloud
Set your API key
Export your Gemini (or OpenAI) API key for ByLLM to use:

bash
Copy code
export BYLLM_API_KEY="your_api_key_here"
▶️ Running the Game
1. Run in CLI mode
This executes the Jac program directly in your terminal:

bash
Copy code
jac run guess_game.jac
2. Run as an API server
Serve the game as a REST API with automatic docs:

bash
Copy code
jac serve guess_game.jac
Once running, open http://localhost:8000/docs to interact with the game API.

📂 Project Structure
bash
Copy code
number-guessing-game/
│── guess_game.jac         # Main Jac program
│── README.md              # Project instructions
🎮 Example Gameplay (CLI)
text
Copy code
> jac run guess_game.jac

Nope! Think higher... maybe it's a lucky number?

Nope! It's higher than that. Think of the number of dwarves in Snow White... plus one!

Nope! Think higher, like reaching for the stars! ✨

Nope! Think of Snow White... how many dwarves were there?

🌐 Example Gameplay (API)

Run the server:

bash
Copy code
jac serve guess_game.jac
Example output in logs:

text
Copy code
Nope! A little higher! Think about what comes after 3... 😉

Congratulations! You guessed correctly.
Too high! Think one lower... like the number of fingers on a ninja turtle's hand!

Nope! But think lower, like the number of legs on a chair!
Test with curl:

bash
Copy code
curl -X POST "http://localhost:8000/guessgame/process_guess" \
     -H "Content-Type: application/json" \
     -d '{"guess": 5}'
✨ Have fun guessing!
