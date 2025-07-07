# OpenAI API Test Runner - Multi-Round Testing

This project allows you to run comprehensive tests with the OpenAI API using multiple prompt templates, science texts, and theoretical frameworks across three rounds of testing.

## Project Structure

```
.
├── .gitignore
├── prompts/
│   ├── template1.txt
│   ├── template2.txt
│   ├── template3.txt
│   ├── template4.txt
│   └── template5.txt
├── variables/
│   ├── science_text/
│   │   ├── science_text_1.txt
│   │   └── science_text_2.txt
│   └── theory/
│       ├── theory_1.txt
│       └── theory_2.txt
├── results/
│   ├── round1/
│   ├── round2/
│   └── round3/
├── README.md
├── requirements.txt
└── run_tests.py
```

## Directory Descriptions

- `prompts/`: Contains text files that serve as templates for the OpenAI API prompts
- `variables/science_text/`: Contains different science texts to be used in testing
- `variables/theory/`: Contains different theoretical frameworks and descriptions
- `results/round1/`, `results/round2/`, `results/round3/`: Store the output from each round of testing
- `run_tests.py`: The main script to execute all rounds of tests

## Setup

1. **Clone the repository** (if you haven't already):
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

2. **Create a virtual environment** (recommended):
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```

3. **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Create a `.env` file**:
    Create a file named `.env` in the root of the project and add your OpenAI API key:
    ```
    OPENAI_API_KEY="your-openai-api-key-goes-here"
    ```

## How to Run

### Basic Usage
Run all three rounds of testing:
```bash
python run_tests.py
```

### What the Script Does

1. **Loads all files**: 
   - All prompt templates from `prompts/`
   - All science texts from `variables/science_text/`
   - All theory frameworks from `variables/theory/`

2. **Runs comprehensive tests**:
   - For each round (1, 2, 3)
   - For each prompt template
   - For each science text
   - For each theory framework
   - Creates all possible combinations

3. **Saves detailed results**:
   - Complete prompt content
   - API response
   - Test metadata (timestamp, files used, model)
   - Results saved in `results/roundX/` with descriptive filenames

### Output Format

Each result file contains:
```
ROUND X TEST RESULTS
==================================================

Timestamp: YYYYMMDD_HHMMSS
Prompt Template: template1.txt
Science Text: science_text_1.txt
Theory Framework: theory_1.txt
Model: gpt-3.5-turbo

COMPLETE PROMPT:
==============================
[Full formatted prompt content]

==============================

API RESPONSE:
==============================
[Complete API response]

==================================================
```

## Customization

### Adding New Templates
1. Create new `.txt` files in the `prompts/` directory
2. Include `{text}` and `{theory}` placeholders as needed
3. Add comments starting with `#` for documentation

### Adding New Science Texts
1. Create new `.txt` files in `variables/science_text/`
2. Include your science content

### Adding New Theories
1. Create new `.txt` files in `variables/theory/`
2. Include your theoretical framework descriptions

### Modifying Test Configuration
Edit `run_tests.py` to change:
- `MODEL_ENGINE`: Change the OpenAI model (e.g., "gpt-4")
- Test rounds: Modify the round numbers in the main function
- File patterns: Change the `*.txt` pattern if needed

## Template Format

Templates should follow this format:
```txt
# Template X: Description
# 🟢 Technique: Technique description
# Purpose: Template purpose
# Usage: Variable usage instructions
# Style: Template style description

[Your prompt content with {text} and {theory} placeholders]

# End of Template X
```

The script automatically removes comment lines (starting with `#`) before processing. 