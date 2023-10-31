# Opti-Q
 
This is a Streamlit app that allows users to ask natural language questions to an Azure OpenAI LLM (Large-Language Model) and get results from an ODP Snowflake database.

This app was adapted from [Frosty](https://quickstarts.snowflake.com/guide/frosty_llm_chatbot_on_streamlit_snowflake).

# Installation
 
You can install the required libraries using:
```
pip install requirements.txt
```

# Configuration

To use the app, you will need to configure the following secrets in your Streamlit app's configuration:
```
[connections.snowflake]
account = "<your_account>"
user = "<your_user>"
password = "<your_password>"
role = "<your_role>"
warehouse = "<your_warehouse>"
client_session_keep_alive = true

[azureopenai]
AZURE_OPENAI_ENDPOINT = "https://<your_endpoint>.openai.azure.com/"
AZURE_OPENAI_KEY = "<your_key>"
AZURE_OPENAI_DEPLOYMENT_NAME = "<your_deployment_name>"
```
You can set these secrets in a secrets.toml file in a folder called .streamlit (i.e., `.streamlit/secrets.toml`) or in the "Secrets" tab of your Streamlit app's configuration.

Additionally, you need to add the fully qualified table names you want to access in `opti-q.py`. 

# Usage

To run the app, run the following command:
```
streamlit run opti-q.py
```

This will start a Streamlit server and launch the app in your browser.

When the app starts, you will see a dropdown menu that allows you to select the table to query. Once you select a table, you can ask natural language questions to the Azure OpenAI LLM by typing in the chat input box and pressing Enter. The LLM will respond with a natural language response, and if it includes a SQL query, the app will execute the query on the Snowflake table and display the results in a DataFrame.
