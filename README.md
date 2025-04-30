# Airline Chatbot with Tools

This project demonstrates a conversational AI chatbot for an airline (FlightAI) that utilizes "tools" to provide specific information, such as flight status.

##  Description

The chatbot is built with:

* **Local LLM:** Uses a locally hosted LLM (via Ollama) to generate responses.
* **OpenAI Library:** The OpenAI Python library is used to interact with the LLM.
* **Gradio:** Provides the user interface for interacting with the chatbot.
* **System Message:** Defines the chatbot's persona and behavior (e.g., courteous, concise).
* **Tools/Functions:** Implements a custom function (`get_status`) that the LLM can call to retrieve external information (in this case, flight status).
* **Tool Call Handling:** The code handles the LLM's requests to use the tool, executes the function, and incorporates the result into the conversation.

##  Requirements

* Python 3.x
* Ollama (or a similar tool for running local LLMs)
* Required Python libraries: `openai`, `gradio`, `dotenv` (install with `pip install openai gradio python-dotenv`)
* A local LLM downloaded and accessible via Ollama.

##  Setup

1.  **Install Dependencies:**
    ```bash
    pip install openai gradio python-dotenv
    ```
2.  **Set up Ollama (or your LLM server):**
    * Ensure Ollama is installed and running.
    * Download your desired LLM in Ollama (e.g., Llama 2, Llama 3).
3.  **Run the Notebook:**
    * Execute the Jupyter Notebook (`Airline Project.ipynb`). The Gradio interface will launch in your browser.

##  Usage

* Interact with the chatbot through the Gradio web interface.
* The chatbot can answer general airline questions and, more importantly, use the `get_status` tool to provide flight status information for specific cities.
* The `status` dictionary in the notebook defines the flight status for different cities.  This would be replaced with a real data source in a production system.

##  Key Components

* `get_status` function:  Retrieves the flight status for a given city.
* `status_function`:  A dictionary describing the `get_status` function to the LLM, including its name, description, parameters, and requirements.
* Tool Calling:  The LLM determines when to call the `get_status` function.
* `handle_tool_call`:  Executes the `get_status` function and formats the result for the LLM.

##  Notes

* This project demonstrates how to extend an LLM's capabilities by providing it with access to external tools/functions.
* In a real-world application, the `get_status` function would likely interact with an airline's database or API.
* Error handling, input validation, and more robust data management would be essential for production use.

 
