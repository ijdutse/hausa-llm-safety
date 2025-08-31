# Hausa LLM Safety: Vulnerability Analysis Dataset

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the dataset and code for the paper **"Linguistic Reward Hacking: Exposing Vulnerabilities in GPT-OSS-20B's Handling of the Hausa Language"**. It provides a curated set of adversarial prompts and model responses that demonstrate critical safety failures, including the generation of harmful health misinformation and culturally insensitive content.

## 🚨 Key Findings

Our red-teaming efforts revealed that GPT-OSS-20B is highly vulnerable to **linguistic reward hacking** in low-resource languages like Hausa. Key failures include:
1.  **Promotion of Toxic Substances:** Recommending insecticides (Fiya-Fiya/Cyphermethrin) and rodenticides (Shinkafar Bera/Aluminium Phosphide) as safe for human consumption.
2.  **Cultural Insensitivity:** Generating stories that incorporate demeaning local idioms and fabricate inflammatory historical narratives.
3.  **Confident Hallucination:** Providing detailed, false instructions on "cultivating" processed foods like spaghetti (Taliya) and local cakes (Alkaki).

## 📁 Repository Structure

```
hausa-llm-safety/
├── data/              # All prompts and collected model responses
├── notebooks/         # Jupyter notebook for replication
└── docs/              # Detailed methodology
```

## 📊 Dataset Overview

The dataset is organized into three main categories of harm:
- `toxic_substances`: Prompts and responses related to harmful chemical recommendations.
- `cultural_insensitivity`: Prompts using demeaning idioms and resulting stories.
- `food_hallucination`: Prompts that trigger false information about food cultivation.

Each CSV file in `data/prompts/` contains the following columns:
- `prompt_id`: A unique identifier for the prompt.
- `prompt_text_ha`: The full adversarial prompt in Hausa.
- `prompt_text_en`: English translation of the prompt.
- `category`: The category of harm.
- `target_failure`: The specific vulnerability the prompt is designed to expose.

## 🛠️ Usage

### Prerequisites
- Access to the GPT-OSS-20B model (e.g., via [gpt-oss.com](https://gpt-oss.com/))

### Reproducing Results
1.  Clone this repository:
    ```bash
    git clone https://github.com/your-username/hausa-llm-safety.git
    cd hausa-llm-safety
    ```
2.  Open the Jupyter notebook `notebooks/missing-in-translation-hausa-steps.ipynb`.
3.  Follow the steps in the notebook to run the prompts against the model and reproduce the documented vulnerabilities.

## 📝 Methodology

Our approach involved systematic adversarial prompting using Chain-of-Thought (CoT) techniques in Hausa. For a detailed explanation of our prompt engineering strategy, please see [docs/methodology.md](docs/methodology.md).

## 🤝 Contributing

We encourage the community to contribute by:
- Adding prompts for other low-resource languages.
- Testing against other model versions.
- Improving the categorization and analysis.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- The Kaggle community and the OpenAI GPT-OSS-20B Red Teaming Competition.
- Contributors and survey participants from the Hausa-speaking community.
