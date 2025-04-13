
## LLMs (Large Language Models)

LLMs are deep learning models trained on massive amounts of text data to **understand and generate human-like language**. They can perform tasks like text generation, translation, summarization, and question answering.

**Examples**

- **GPT (Generative Pretrained Transformer)** – Text generation, conversational AI.
- **BERT (Bidirectional Encoder Representations from Transformers)** – Text understanding, sentiment analysis.
- **T5 (Text-to-Text Transfer Transformer)** – Multi-task text generation and transformation.


# Vectors
In machine learning and AI, a **vector** is a list (or array) of **numerical values**. These numbers represent a **point** in a multi-dimensional space.

- Each number in the vector is called a **dimension**.
- For example, a vector could be `[2, 5, 3]`, which has 3 dimensions (x, y, and z).

In the case of **word embeddings**, a word like "cat" is represented as a vector, where each number in the vector reflects a feature of the word, such as its meaning, context, or relationship to other words.

## Why We Use Vectors
Vectors allow us to:

1. **Numerically represent words or data**: Words themselves are not numbers, but by converting them to vectors, we make them usable in mathematical models.
2. **Capture relationships and similarities**: The distance between two vectors can show how similar two words are. For example, the vector for "king" might be close to the vector for "queen" because they share similar meanings.

## Example of a Vector Representation
A word like "apple" might be represented as a vector like `[0.1, 0.2, 0.3, 0.4]`, where:
- `0.1` might correspond to the word's **fruit-related meaning**.
- `0.2` could represent its **sweetness**.
- `0.3` might capture **its association with technology** (like Apple Inc.).
- `0.4` could relate to **color or shape**.

Each dimension in the vector represents a feature that helps the model understand the word better.

## Why Vectors Are Important
Vectors allow models to:
- **Process words as numbers**, making it easier to apply mathematical operations (like calculating similarities or differences).
- **Capture context**: A vector for the word "bank" in a financial context will be different from one in a riverbank context, allowing models to handle polysemy (words with multiple meanings).


## How Vectors Capture Word Context

### Meaning of Vectors in Context
When we convert words into vectors (using **embeddings**), each word gets a **numerical representation** that captures its **meaning** based on **context**. This is achieved by training the model on large amounts of text where it learns how words are used in different situations.

- **Context matters**: If the word "orange" is used in a sentence like "I ate an orange," the model learns that "orange" refers to a **fruit**. If it’s used in "The sky is orange," the model learns that it refers to a **color**.

#### How Context is Captured
Embeddings are generated using techniques like **Word2Vec** or **GloVe**. These methods assign words to vectors based on their **co-occurrence** with other words in different contexts.

**Example 1: Word2Vec (Skip-Gram Model)**

- When the word "orange" is used in a sentence like "I ate an orange," the model will learn that "orange" often appears near words like **fruit**, **delicious**, **eat**.
- When used in "The sky is orange," it will often appear near words like **color**, **sunset**, **sky**.
  
The model will generate **different vectors** for "orange" in these contexts because of the surrounding words. These vectors will reflect the specific context of the word in each case.

**Example 2: GloVe (Global Vectors for Word Representation)**

- GloVe looks at the **global context** of words across an entire corpus. It learns that "orange" shares different co-occurrence statistics with words like **fruit** and **color**.
- The resulting vectors will still be **close to each other**, but they’ll be distinct enough to represent different meanings in different contexts.

#### Dimensionality and Contextual Representation
Each vector typically has many dimensions (e.g., 300-dimensional). Each dimension doesn’t directly correspond to a specific meaning like "sweetness" or "color," but rather represents **latent features** learned from data. These features emerge from how words relate to other words in sentences.

**For Example:**
- **Context 1**: "I ate an orange" – The vector might emphasize features related to **edible**, **fruit**, and **taste**.
- **Context 2**: "The sunset was orange" – The vector might emphasize features related to **color**, **sky**, and **nature**.

#### Word Sense Disambiguation (WSD)
Models like **BERT** or **GPT** are designed to handle this. They consider the full sentence (or even larger context) to adjust the vector of a word dynamically. This process is called **contextual embedding**, where the same word might have slightly different vector representations depending on its usage.

#### Why Vectors Capture Context
By using large corpora of text, embeddings capture the **statistical relationship** between words in various contexts. This allows models to differentiate meanings like:
- "Orange" as a **fruit** when surrounded by words like "eat," "juice," and "sweet."
- "Orange" as a **color** when surrounded by words like "sky," "sunset," and "bright."

Thus, **vectors** represent both the general meaning of the word and its specific meaning in context.


# Tokenization, Embeddings, and Transformers

## Tokenization
Tokenization is the process of breaking down text into smaller pieces, such as words, subwords, or characters. These tokens are then fed into models for processing.

- **Why We Need It**: Tokenization allows the model to handle text in manageable units. It’s necessary because the model needs a consistent format to understand and process varying-length input.

- **Example**: "I love AI" becomes `['I', 'love', 'AI']`.

## Embeddings
Embeddings are dense vector representations of tokens. Each token is mapped to a vector of numbers that capture its meaning based on context.

- **Why We Need It**: Embeddings allow words to be represented in a way that preserves their semantic meaning. Unlike traditional one-hot encoding, which only shows whether a word exists or not, embeddings capture **context** and **relationships** between words.

- **Word Embedding Example**: The word "cat" might be represented as `[0.1, 0.2, 0.3, ...]` in a multi-dimensional space.

## Transformers
Transformers are a type of neural network architecture that processes input data in **parallel** rather than sequentially, making them highly efficient. They use **self-attention mechanisms** to focus on different parts of the input sequence for better context understanding.

- **Why We Need It**: 
Transformers are crucial because they handle long-range dependencies in text and process data much faster than older models like RNNs. **Self-attention** helps the model focus on relevant parts of the input sequence, even if they are far apart in the text.

- **Key Concepts**:
    - **Self-Attention**: Allows the model to consider all parts of the input sequence at once, making it more efficient for tasks requiring context from multiple parts of the text.
    - **Positional Encoding**: Adds information about the order of tokens, ensuring the model understands the sequence of the input.
  
- **Popular Transformers**:
    - **GPT**: Focuses on autoregressive text generation.
    - **BERT**: Focuses on bidirectional context understanding.
