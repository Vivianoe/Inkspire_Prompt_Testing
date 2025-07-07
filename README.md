# OpenAI API Prompt Testing Project

This project enables structured, multi-round prompt testing with the OpenAI API. It supports batch testing of multiple prompt templates, science texts, and theoretical frameworks, and automatically saves all results for later analysis.

## Project Structure

```
.
├── .gitignore
├── prompts/
│   ├── template1.txt
│   ├── template2.txt
│   ├── template3.txt
│   └── template4.txt
├── variables/
│   ├── science_text/
│   │   ├── science_text1.txt
│   │   ├── science_text2.txt
│   │   └── science_text3.txt
│   └── theory/
│       ├── theory_1.txt
│       ├── theory_2.txt
│       └── theory_3.txt
├── results/
│   ├── round1/
│   ├── round2/
│   └── round3/
├── run_tests.ipynb
├── requirements.txt
└── README.md
```

## Directory Descriptions

- `prompts/`: Prompt templates for the OpenAI API. Each template is a `.txt` file with placeholders for variables.
- `variables/science_text/`: Science text files (e.g., `science_text1.txt`, `science_text2.txt`, ...).
- `variables/theory/`: Theoretical framework files (e.g., `theory_1.txt`, `theory_2.txt`, ...).
- `results/round1/`, `results/round2/`, `results/round3/`: Output directories for each test round. Each result file contains the full prompt and the API response.
- `run_tests.ipynb`: Jupyter notebook for running and analyzing prompt tests interactively.
- `requirements.txt`: Python dependencies.

## Setup

1. **Clone the repository**
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```
2. **Create a virtual environment** (recommended)
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```
3. **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```
4. **Create a `.env` file**
    Add your OpenAI API key:
    ```
    OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
    ```

## How to Use

### Interactive Notebook
- Open `run_tests.ipynb` in Jupyter Lab/Notebook.
- Follow the notebook cells to run multi-round prompt tests and save results automatically.

### Project Logic
- **Round 1:**
  - Test `template1.txt`, `template2.txt`, `template3.txt`.
  - For each template, use `theory_1.txt`.
  - For each template, iterate over all science texts (`science_text1.txt`, `science_text2.txt`, `science_text3.txt`).
  - Results are saved in `results/round1/`.
- **Round 2:**
  - Test only `template3.txt`.
  - For `template3.txt`, iterate over all science texts and all theory files (`theory_1.txt`, `theory_2.txt`, `theory_3.txt`).
  - Results are saved in `results/round2/`.
- **Round 3:**
  - Reserved for future custom tests.

### Output Format
Each result file contains:
```
PROMPT:
==============================
[Full formatted prompt content]

RESULT:
==============================
[Complete API response]
```

## Customization

- **Add new prompt templates:** Place `.txt` files in `prompts/` with `{text}` and `{theory}` placeholders.
- **Add new science texts:** Place `.txt` files in `variables/science_text/`.
- **Add new theories:** Place `.txt` files in `variables/theory/`.
- **Modify test logic:** Edit `run_tests.ipynb` to change which templates, texts, or theories are used in each round.

## Template Format Example

```txt
# Template X: Description
# Technique: ...
# Purpose: ...
# Usage: ...
# Style: ...

[Prompt instructions with {text} and {theory} placeholders]

# End of Template X
```

> The notebook automatically removes comment lines (starting with `#`) before sending prompts to the API.

## License

This project is for research and educational use. Please comply with OpenAI's API terms of service. 