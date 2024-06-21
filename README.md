# Population and Demographics Query Agent

<image src="https://talkie.ai/app/uploads/2022/02/what-are-virtual-agents.jpg">

This project implements a query agent that uses various data sources to provide information about world population and demographics, as well as specific information about Canada. The agent uses OpenAI's GPT-3.5-turbo model and several custom query engines to process and respond to user prompts.

## Features

- Query population data from a CSV file.
- Query detailed information about Canada.
- Use OpenAI's GPT-3.5-turbo model for natural language understanding and response generation.
- Customizable query prompts and context.

## Requirements

- Python 3.7 or higher
- Required Python libraries:
  - pandas
  - python-dotenv
  - llama-index

## Installation

1. Clone the repository:

    ```bash
    git clone git@github.com:matinsajadii/agent-ai.git
    cd yourrepository
    ```

2. Create and activate a virtual environment:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

4. Create a `.env` file in the root directory of the project and add your OpenAI API key:

    ```
    OPENAI_API_KEY=your_openai_api_key
    ```

5. Place your `population.csv` file in the `data` directory.

## Usage

1. Run the script:

    ```bash
    python main.py
    ```

2. Enter a prompt at the prompt (e.g., "What is the population of Canada?"). Type `q` to quit.

## Code Overview

- `main.py`: The main script that sets up and runs the query agent.
- `note_engine.py`: Custom tool for note-taking or additional data processing (implementation not shown here).
- `pdf.py`: Custom tool to handle PDF documents and extract information (implementation not shown here).
- `prompts.py`: Contains the custom prompts and context for the query agent.

### Key Components

- **Environment Variables**: Loaded using `dotenv` to securely handle API keys.
- **Data Loading**: Population data is loaded from a CSV file into a pandas DataFrame.
- **Query Engines**: Custom `PandasQueryEngine` is used to query the population data.
- **Tools**: List of tools including custom engines and metadata descriptions.
- **ReActAgent**: The main query agent that processes user prompts using the provided tools and OpenAI's GPT-3.5-turbo model.

## Customization

- **Prompts and Context**: Modify `prompts.py` to change the instruction strings and context used by the agent.
- **Additional Tools**: Implement additional tools and query engines as needed and add them to the `tools` list in `main.py`.

## Example

```python
Enter a prompt (q to quit): What is the population of Canada?
```

The agent will process the prompt and return relevant information based on the population data and other tools.

## Contributing

Feel free to submit issues or pull requests if you have suggestions or improvements.

## License

This project is licensed under the MIT License. See the LICENSE file for more details.
