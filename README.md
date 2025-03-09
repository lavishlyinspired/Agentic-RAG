# AgenticRAG Deployment Guide

This guide will help you set up and run the `AgenticRAG.ipynb` notebook in VS Code.

## Prerequisites

Make sure you have the following installed:
- [Python 3.8+](https://www.python.org/downloads/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Jupyter extension for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter)
- [pip](https://pip.pypa.io/en/stable/)
- (Optional) [Anaconda](https://www.anaconda.com/) if using Conda

## Setting Up the Environment

### Option 1: Using `venv`

1. Open a terminal in the project directory.
2. Create a virtual environment:
   ```sh
   python -m venv venv
   ```
3. Activate the environment:
   - **Windows:**
     ```sh
     venv\Scripts\activate
     ```
   - **Mac/Linux:**
     ```sh
     source venv/bin/activate
     ```
4. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```

### Option 2: Using Conda

1. Open a terminal and create a new Conda environment:
   ```sh
   conda create --name agenticrag_env python=3.8
   ```
2. Activate the environment:
   ```sh
   conda activate agenticrag_env
   ```
3. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```

## Running the Notebook in VS Code

1. Open VS Code and install the **Jupyter extension** if not already installed.
2. Open the `AgenticRAG.ipynb` notebook in VS Code.
3. Select the appropriate Python interpreter (your virtual/Conda environment).
4. Run the cells in the notebook.

## Dependencies

If `requirements.txt` is missing, install the required packages manually:
```sh
pip install IPython dotenv langchain langchain_community langchain_core langchain_groq langchain_openai langchain_text_splitters langgraph pydantic
```
Then, generate a `requirements.txt` file:
```sh
pip freeze > requirements.txt
```

## Environment Variables

If the notebook relies on environment variables (e.g., API keys), create a `.env` file in the project directory:
```sh
OPENAI_API_KEY=your_api_key_here
```
Ensure the `.env` file is loaded in the notebook using:
```python
from dotenv import load_dotenv
load_dotenv()
```

## Troubleshooting

- If Jupyter is not found in VS Code, install it:
  ```sh
  pip install notebook
  ```
- If dependencies are missing, reinstall them using:
  ```sh
  pip install -r requirements.txt
  ```
