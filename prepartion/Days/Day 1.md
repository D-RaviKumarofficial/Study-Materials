# GenAI Interview: 5 Questions with Simple Answers

Speak slowly. Use these answers in your own words.

---

## 1. What is RAG? Why do we use it?

**Answer:**
RAG means Retrieval Augmented Generation. The LLM does not know our private data, so we give the data to it.

Steps:
1. Take our documents (PDF, Word) and cut them into small pieces. These are called chunks.
2. Convert each chunk into numbers. These are called embeddings.
3. Store them in a vector database like Pinecone.
4. When the user asks a question, convert the question into numbers also.
5. Find the chunks most similar to the question.
6. Send those chunks and the question to the LLM.
7. The LLM reads them and gives the answer.

**Why we use it:**
- The answer comes from our real data, so there are fewer wrong answers.
- The LLM can use private and new data.
- It is cheaper than training the model again.

---

## 2. Users say RAG answers are wrong. How do you debug?

**Answer:**
First I check the retrieval part. If the right chunk is not coming, the LLM cannot give the right answer.

**Retrieval problems:**
- Chunk size is too big or too small. I change the size and add some overlap.
- Documents and questions use different embedding models. Both must use the same model.
- Exact words like product codes are missed. I use keyword search along with vector search.
- Top-k is too low. I get more chunks and then pick the best ones using a re-ranker.

**Generation problems:**
- The prompt does not say "answer only from the given context". I fix the prompt.
- Too much context is sent. I send fewer chunks.

I also make a test set of questions with known answers, so I can check where the problem is.

---

## 3. What is an AI agent? How is it different from a normal chatbot?

**Answer:**
A normal chatbot takes the question and gives the answer from the model. That is all.

An agent can use tools and take actions. For example, read, edit and delete in a database. It works in a loop:
1. Think about what to do.
2. Call a tool.
3. Look at the result.
4. Repeat until the task is done.

**Example:** User says "update employee 101". The agent checks if employee 101 exists, then calls the edit tool, then tells the user it is done. If there is an error, it tries again or tells the user.

**Important:** For edit and delete, I ask the user to confirm first. I also give the agent only the access it needs.

---

## 4. What is MCP? Why do we need it?

**Answer:**
MCP means Model Context Protocol. It is a common standard to connect AI applications with tools and data.

**Problem before MCP:** Every AI app needed separate code for every tool. That is a lot of work.

**With MCP:** I build one MCP server for a tool, like our employee database. Then any AI app that supports MCP can use it.

Think of it like a USB-C port. One standard works with everything.

**Parts:**
- Host: the AI app.
- Client: inside the host, connects to the server.
- Server: wraps the tool or data and gives it to the AI.

A server can give tools (actions), resources (data to read) and prompts (ready templates).

---

## 5. What is the difference between RAG and fine-tuning?

**Answer:**
The difference is where the new information goes.

- **RAG:** The model does not change. I give the information in the prompt when the user asks. It is like an open book exam.
- **Fine-tuning:** I train the model and change its weights. It is like studying before the exam.

**Use RAG when:**
- Data changes often, like policies and prices.
- Data is private.
- I want to show the source of the answer.

**Use fine-tuning when:**
- I want a fixed style or format of answer.
- I want a small model to do one task well.

**Remember:** For facts and knowledge, I start with RAG. Fine-tuning is costly and the facts get old. Many projects use both together.

---

## If you do not know an answer

Say this honestly: "I have not worked on this directly, but my understanding is..." and then explain what you know. It is better than guessing.
