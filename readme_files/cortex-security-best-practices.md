# Security Best Practices for Cortex AI

When building AI agents, security must be a top priority. Snowflake Cortex is designed with security in mind, but administrators still need to enforce best practices.

## 1. Role-Based Access Control (RBAC)
Always ensure that the Cortex Search Service is bound to specific Snowflake roles. Users should only be able to query the agent if they have read access to the underlying table.

## 2. Masking PII
Before chunking and indexing text, use Snowflake's dynamic data masking or masking policies to redact Personally Identifiable Information (PII) from the raw articles.
