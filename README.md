# Text-to-SQL — Natural Language to SQL

An AI-powered **Text-to-SQL system** that converts natural-language questions into SQL queries using the **OpenAI API**.

The project allows users to interact with data using natural language instead of manually writing SQL queries.

For example:

```text
User:
"Show me the top 5 customers by total purchase amount."

        ↓

AI Text-to-SQL System

        ↓

SELECT customer_name, SUM(amount) AS total_purchase
FROM sales
GROUP BY customer_name
ORDER BY total_purchase DESC
LIMIT 5;
```

---

## Features

- Convert natural-language questions into SQL queries
- Uses OpenAI models for natural-language understanding
- Automatically generates SQL based on the provided database/schema context
- Designed for querying structured data
- Reduces the need to manually write SQL
- Implemented in Google Colab
- Uses Google Colab Secrets for secure API-key handling
- Open-source and easy to experiment with

---

## Workflow

```text
Natural Language Question
          ↓
     User Input
          ↓
   Prompt Construction
          ↓
      OpenAI API
          ↓
     SQL Generation
          ↓
   Generated SQL Query
          ↓
    Database Execution
          ↓
      Query Result
```

---

## Example

### Natural Language Input

```text
Show me all employees whose salary is greater than 50000.
```

### Generated SQL

```sql
SELECT *
FROM employees
WHERE salary > 50000;
```

The generated SQL can then be executed against the configured database to retrieve the corresponding results.

---

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| OpenAI API | Natural-language understanding and SQL generation |
| SQL | Database querying |
| Google Colab | Development and execution environment |
| Pandas | Data handling and analysis |
| SQLite / Database | Data storage and querying |

> Note: Update the database/library entries above if your implementation uses a different database or additional technologies.

---

## Project Structure

```text
text-to-sql/
│
├── Text_to_SQL.ipynb
├── README.md
└── requirements.txt
```

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/text-to-sql.git
```

### 2. Open the notebook

Open:

```text
Text_to_SQL.ipynb
```

in Google Colab.

### 3. Configure the API key

Add your own:

```text
OPENAI_API_KEY
```

through Google Colab Secrets.

### 4. Run the notebook

Execute the notebook cells in order and provide a natural-language question.

---

## API Key Setup

For security reasons, **no OpenAI API key is stored in this repository**.

The project uses **Google Colab Secrets** to securely access the API key.

The notebook uses:

```python
from google.colab import userdata
import os

api_key = userdata.get("OPENAI_API_KEY")
os.environ["OPENAI_API_KEY"] = api_key
```

### Setting Up Your API Key

When running the project in Google Colab:

1. Open the notebook in Google Colab.
2. Open the Secrets panel from the left sidebar.
3. Create a secret named:

```text
OPENAI_API_KEY
```

4. Enter your own OpenAI API key.
5. Enable notebook access for the secret.
6. Run the notebook.

**Never add your actual API key directly to the notebook or GitHub repository.**

---

## Example Queries

The system can be used with questions such as:

```text
How many customers are there?
```

```text
Show the top 10 products by sales.
```

```text
What is the average salary of employees?
```

```text
Which department has the highest number of employees?
```

```text
Show all orders placed in 2025.
```

The system converts the natural-language request into an SQL query based on the available schema and data context.

---

## Why Text-to-SQL?

Traditional database systems require users to understand SQL syntax before they can retrieve information.

Text-to-SQL provides a more accessible interface:

```text
Traditional Approach

User → SQL Knowledge → SQL Query → Database → Result


Text-to-SQL Approach

User → Natural Language → AI → SQL Query → Database → Result
```

This makes structured data easier to access for users who may not have extensive SQL knowledge.

---

## Limitations

- Generated SQL may occasionally be incorrect.
- The quality of the generated query depends on the database/schema information provided to the model.
- Complex database relationships may require additional prompt engineering.
- OpenAI API usage requires an API key.
- API usage may incur costs depending on the selected model and usage.
- Generated SQL should be validated before executing it against important or production databases.

---

## Security

The project is designed so that the OpenAI API key is **not included in the GitHub repository**.

Instead, the key is retrieved from Google Colab Secrets:

```python
userdata.get("OPENAI_API_KEY")
```

This allows the source code and project workflow to remain publicly visible while keeping the API credential private.

---

## Future Improvements

- [ ] Support for multiple database types
- [ ] Automatic database schema detection
- [ ] SQL query validation
- [ ] SQL error correction
- [ ] Conversational follow-up questions
- [ ] Query history
- [ ] Interactive data visualization
- [ ] Database upload functionality
- [ ] Streamlit/Gradio interface
- [ ] RAG-based schema retrieval
- [ ] Query optimization
- [ ] Support for more complex joins and nested queries

---

## Potential Applications

Text-to-SQL systems can be useful for:

- Business intelligence
- Data analytics
- Database exploration
- Reporting systems
- Customer analytics
- Sales analytics
- Financial data analysis
- Natural-language dashboards
- Data science applications

---

## Important Note

This project is intended for **learning, experimentation, and demonstration purposes**.

AI-generated SQL should be reviewed and validated before being executed against sensitive or production databases.

---

## Author

**Aryan Mathuriya**

B.Tech — Artificial Intelligence & Data Science

GitHub:

`https://github.com/Aryanior`

---

## Support

If you find this project useful, consider giving the repository a star on GitHub.
