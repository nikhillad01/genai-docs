# Prompt Engineering Basics

## Zero-shot Prompting
Ask the model to perform a task with **no examples**.

- **Example**:  
  "Write a Python function to sort a list of integers."

- **Why it's useful**:  
  Good for simple, well-understood tasks where the model can rely on its pretraining.

## One-shot Prompting
Provide **one example** to guide the model's behavior.

- **Example**:  
  "Convert a Python list to a JSON string.  
  Input: [1, 2, 3]  
  Output: '[1, 2, 3]'  
  Input: ['a', 'b', 'c']  
  Output:"

- **Why it's useful**:  
  Clarifies the expected input-output format, especially when ambiguity exists.

## Few-shot Prompting
Provide **2–5 examples** to show the pattern clearly.

- **Example**:  
  "Convert a Python snippet to equivalent JavaScript.  
  Python: `print('Hello')`  
  JS: `console.log('Hello');`  
  Python: `len([1,2,3])`  
  JS: `[1,2,3].length`  
  Python: `range(5)`  
  JS:"

- **Why it's useful**:  
  Boosts accuracy by showing consistent translation logic across multiple examples.

## Prompt Chaining
Break down a complex task into **smaller sub-prompts**, passing output from one step to the next.

- **Example**: Generating API documentation
  1. Prompt 1: "Summarize what this FastAPI function does."
  2. Prompt 2: "Generate an OpenAPI description from the summary."
  3. Prompt 3: "Convert OpenAPI to Markdown format."

- **Why it's useful**:  
  Keeps each step focused and manageable. Helps reduce hallucination and improves control over complex workflows.
