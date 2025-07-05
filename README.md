# LangChain Memory & LCEL

This project demonstrates various concepts and practical examples using LangChain, focusing on memory, LCEL (LangChain Expression Language), and Retrieval-Augmented Generation (RAG) workflows.

## Topics Covered

### 1. Environment Setup

- Loads environment variables using `python-dotenv` to securely access API keys (e.g., `GROQ_API_KEY`).

### 2. Using Groq LLM with LangChain

- Initializes a `ChatGroq` model with custom parameters (model name, temperature, max tokens, etc.).
- Demonstrates how to use the model in a chain for text generation.

### 3. Prompt Templates and Output Parsing

- Uses `ChatPromptTemplate` to create dynamic prompts.
- Parses model outputs with `StrOutputParser`.

### 4. LCEL Chains

- Shows how to compose chains using the LCEL syntax: `prompt | model | output_parser`.
- Demonstrates invoking chains with input variables.

### 5. Using `.bind()` in LCEL

- Illustrates how to use `.bind()` to add arguments (e.g., stop sequences) to a Runnable in a chain.

### 6. Combining LCEL Chains

- Demonstrates combining multiple chains, including passing outputs from one chain as inputs to another.
- Example: Generating a sentence about a politician, then using that output in a follow-up prompt.

### 7. Nested Chains (Chain inside another Chain)

- Shows how to nest chains and use `itemgetter` to pass variables between them.
- Example: Determining a politician's country, then asking about the continent in a specified language.

### 8. Retrieval-Augmented Generation (RAG) with LCEL

- Loads and parses web content using `WebBaseLoader` and BeautifulSoup.
- Splits documents into chunks with `RecursiveCharacterTextSplitter`.
- Embeds documents using HuggingFace embeddings.
- Stores and retrieves documents with Chroma vectorstore.
- Formats retrieved documents for context in prompts.
- Builds a RAG chain that answers questions based on retrieved context.

### 9. Example RAG Queries

- Demonstrates querying the RAG chain for answers to questions like "What is Task Decomposition?" and "What is the difference between a task and a subtask?"

## Requirements

See [requirements.txt](d:/AI/LangChain%20Memory%20&%20LCEL/requirements.txt) for the full list of dependencies.

## Usage

Open [LangChain_Memory_LCEL.ipynb](d:/AI/LangChain%20Memory%20&%20LCEL/LangChain_Memory_LCEL.ipynb) in Jupyter or VS Code and run the cells to explore each topic

# LangChain Memory

This project demonstrates how to use different memory types in LangChain to enable conversational context and history in LLM-powered applications.

## Topics Covered

### 1. Environment Setup

- Loads environment variables using `python-dotenv` for secure API key management (e.g., `GROQ_API_KEY`).

### 2. Using Groq LLM with LangChain

- Initializes a `ChatGroq` model with custom parameters for use in conversational chains.

### 3. Conversation Buffer Memory

- **ConversationBufferMemory** keeps a list of all chat messages in a buffer and passes them into the prompt template.
- Demonstrates how to set up a prompt with `MessagesPlaceholder` to inject chat history.
- Shows how to use `LLMChain` with buffer memory to maintain conversation state.
- Example: The model remembers the user's name and occupation across multiple turns.

### 4. Inspecting Memory Buffer

- Shows how to print the memory buffer to inspect the stored conversation history.

### 5. Conversation Buffer Window Memory

- **ConversationBufferWindowMemory** keeps only the most recent `k` messages in memory.
- Demonstrates how to use `ConversationChain` with window memory to limit the context window.
- Example: Only the last 3 exchanges are remembered by the model.

## Requirements

See `requirements.txt` for the full list of dependencies.

## Usage

Open `Memory_langchain.ipynb` in Jupyter or VS Code and run the cells to explore each
