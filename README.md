# Enterprise Customer Support System - README

## Overview
The Enterprise Customer Support System is an AI-powered chatbot designed to assist users with product-related queries. It utilizes OpenAI's GPT-3.5-turbo and FAISS-based vector search to retrieve relevant information from product documentation.

## Installation
To install the required dependencies, run the following command:

```sh
pip install -U langchain-community faiss-cpu sentence-transformers huggingface-hub langchain-core
```

## Setup Instructions

1. **Set Up OpenAI API Key**
   - Replace `'sk-proj-XXXXX'` in the script with your actual OpenAI API key.
   - Alternatively, set it as an environment variable:
     
     ```sh
     export OPENAI_API_KEY='your_api_key_here'
     ```

2. **Initialize Embeddings and Vector Store**
   - The system uses `sentence-transformers/all-mpnet-base-v2` for text embeddings.
   - FAISS is used to store and retrieve vectorized product documentation.

3. **Define Product Documentation**
   - The chatbot is preloaded with documentation for Product A, Product B, and Product C.
   - Customize the `product_docs` dictionary with your own content.

4. **Customize Memory and LLM**
   - A `ConversationBufferWindowMemory` object maintains short-term memory of conversations.
   - The system uses OpenAI's GPT-3.5-turbo with a temperature of `0.2`.

## Example Usage Scenarios

### Querying Product Information
Users can ask general product-related questions, such as:

```sh
How do I troubleshoot Product A?
```

**Expected Response:**
- Retrieves relevant documentation and provides troubleshooting steps.

### Checking Order Status
Users can check the order status using a special command:

```sh
#orderstatus ORD12345
```

**Expected Response:**
- Returns order status and expected delivery date.

### Escalating Issues
If users need to escalate an issue, they can use:

```sh
#escalate Can't login to Product B|urgent
```

**Expected Response:**
- Generates a support ticket with a priority label.

### Running the Chatbot
Run the script in interactive mode for a chatbot-like experience:

```sh
python script.py
```

Example interaction:

```
Customer query: What are the system requirements for Product C?
Support Agent: Product C requires iOS 14+ or Android 10+ with a minimum of 2GB RAM.
```

## Conclusion
This chatbot enhances customer support by integrating AI-powered document retrieval and intelligent response generation. Modify the `product_docs` dictionary and fine-tune model parameters for better results.

 
