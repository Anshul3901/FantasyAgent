# Fantasy Football AI Agent

## Overview

The **Fantasy Football AI Agent** is an AI-powered assistant designed to help fantasy football managers make smarter decisions. Leveraging large language models (LLMs), player statistics, injury histories, and Yahoo Fantasy integration, this tool provides data-driven recommendations, lineup optimization, waiver analysis, and more—all through an interactive chat interface.

## Features
- **Conversational AI**: Ask questions about players, trades, lineups, and get detailed, data-backed answers.
- **Yahoo Fantasy Integration**: View your team roster, available waiver players, and league standings (requires Yahoo API credentials).
- **Data-Driven Analysis**: Utilizes combine data, injury history, and performance stats for recommendations.
- **Customizable League Rules**: Supports PPR scoring and standard fantasy league formats.
- **Streamlit Web App**: User-friendly chat interface with quick question buttons and team info.
- **Command-Line Interface**: Interact with the agent directly from the terminal.

## Directory Structure
```
FantasyAgent/
├── app.py                # Streamlit web app
├── main.py               # Command-line interface
├── requirements.txt      # Python dependencies
├── verify_setup.py       # Setup and data verification script
├── oauth.json            # Yahoo API credentials (user-provided)
├── src/
│   ├── agent/            # AI agent logic and tools
│   ├── data/             # Data loading and processing
│   ├── utils/            # Utilities (Yahoo API, config, chat formatting)
│   └── ...
├── storage/
│   └── fantasy/          # Vector stores and indexes (auto-generated)
└── ...
```

## Installation
1. **Clone the repository**
   ```bash
   git clone <repo-url>
   cd FantasyAgent
   ```
2. **Create a virtual environment (recommended)**
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Configuration
1. **Environment Variables**
   - Create a `.env` file in the project root with your OpenAI API key:
     ```env
     OPENAI_API_KEY=your-openai-api-key
     ```
2. **Yahoo API Credentials**
   - Place your `oauth.json` (Yahoo OAuth2 credentials) in the project root. This is required for Yahoo Fantasy integration.

## Data Requirements
Place the following CSV files in `src/data/Dataset/`:
- `combine_data.csv`   (NFL Combine Performance Data)
- `injuries.csv`       (Player Injury History)
- `rush.csv`           (Rushing Statistics)

Other optional files (if available):
- `ftn_charting.csv`, `tackle_nfl.csv`, `team_rosters.csv`

You can verify your setup and data files by running:
```bash
python verify_setup.py
```

## Usage
### Streamlit Web App
Launch the interactive chat interface:
```bash
streamlit run app.py
```
- Ask questions about players, lineups, trades, and more.
- View your team, available players, and league info in the sidebar.

### Command-Line Interface
Interact with the agent in your terminal:
```bash
python main.py
```
- Type your questions and get instant responses.
- Type `quit` to exit.

## Notes
- Make sure your Yahoo league ID is set correctly in `src/utils/yahoo_fantasy.py` if you want to use Yahoo integration.
- The app requires internet access for LLM and Yahoo API calls.
- For best results, keep your data files up to date.

## License
This project is for educational and personal use. Not affiliated with the NFL, Yahoo, or OpenAI. 