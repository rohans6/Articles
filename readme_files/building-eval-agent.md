# Building an AI Evaluation Agent

In this tutorial, we will explore how to evaluate web articles and GitHub repositories using Snowflake Cortex. 

## The Pipeline
First, you need to ingest the articles into Snowflake. You can use External Network Access (ENA) or Openflow to pull Markdown files directly into a Snowflake table. 

## The Evaluation Prompt
Once your data is in the `processed_github_articles` table, you can evaluate the content using the Llama 3 model:

```sql
SELECT 
    file_name,
    SNOWFLAKE.CORTEX.COMPLETE(
        'llama3-8b',
        CONCAT('Analyze this article and extract the main topic: ', article_content)
    )
FROM processed_github_articles;
```
