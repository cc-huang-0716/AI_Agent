# AI Agent with Financial Analysis Capabilities

This project implements an AI agent for financial analysis using Langchain, Hugging Face, FAISS, and Yahoo Finance. It can handle portfolio volatility calculations, text document searches, and LLM-based general queries.

## Features

1. **Portfolio Volatility Calculation** - Calculate portfolio risk based on historical stock price data from Yahoo Finance.
2. **Financial Knowledge Retrieval** - Retrieve relevant financial information from a pre-processed text document.
3. **General Query Response** - Use an external LLM for open-ended questions.

## Prerequisites

* Python 3.9+
* Hugging Face API Token
* Required Python libraries:

  * `langchain`
  * `requests`
  * `numpy`
  * `pandas`
  * `yfinance`
  * `faiss-cpu`

Install the necessary packages:

```bash
pip install langchain requests numpy pandas yfinance faiss-cpu
```

## Setup

1. Clone this repository:

```bash
git clone https://github.com/cc-huang-0716/AI_Agent.git
cd AI_Agent
```

2. Set up the Hugging Face API token:

```bash
export HUGGINGFACEHUB_API_TOKEN='your_huggingface_token'
```

3. Download the text file:

Replace the link in the `txt_url` variable if you have a custom file:

```python
txt_url = "https://drive.google.com/file/d/1w9gy6GJYbUxtqqTrcdu4su3N6cyexYME/view?usp=drive_link"
```

4. Run the main script:

```bash
python main.py
```

## Usage

You will be prompted to select the type of query:

1. **Portfolio Volatility Calculation**

   * Format: `AAPL,MSFT,GOOGL;0.4,0.3,0.3`
2. **Financial Knowledge Retrieval**

   * Ask finance-related questions based on the pre-processed text file.
3. **General Query Response**

   * Use the LLM for general questions.

## Customization

* **LLM Model** - You can replace the LLM model in the code:

```python
llm = HuggingFaceEndpoint(
    repo_id="meta-llama/Llama-2-7b-chat-hf",
    temperature=0.7,
    huggingfacehub_api_token=os.environ["HUGGINGFACEHUB_API_TOKEN"]
)
```

* **Text Document** - Replace the `txt_url` in the code to use a different document.
