# Philosophers-Debate-Simulator
The goal of this project is to improve how philosophy is studied by moving away from rote memorization toward AI-powered dialogue simulations.
We use classical philosophical texts (e.g., Aristotle’s Physics) to build a searchable vector database.
When users input a philosophical question, such as "What is justice?" or "What is love?", the system retrieves relevant text segments and simulates how each philosopher might respond, preserving their unique reasoning styles.

## Project Description

This project was created as the final assignment for the Introduction to Artificial Intelligence course at National Chengchi University in 2025.

In everyday life, we constantly face decisions, ranging from small ones like "What should I eat for dinner?", to life-changing ones like "Which college should I go to?" People often find themselves torn between options, lacking a clear, well-reasoned perspective.

That’s where our idea came from: what if we could simulate a debate between two “experts” from opposing philosophical perspectives to help users explore the pros and cons of their decisions?

Our goal was to build an AI tool that simulates an intellectual debate between two philosophers with opposing perspectives to help users explore complex decisions through philosophical reasoning. We constructed two LangChain-powered AI agents, each connected to its own custom database built from classical texts, to represent the ideas and language styles of each philosopher.

This project integrates:
 * PDF preprocessing of classical texts
 * OpenAI embeddings
 * MongoDB Atlas vector search
 * LangChain framework for retrieval
 * Gradio for interactive UI

## Getting Started

To run this project locally or build upon it, you’ll need the following:

### Prerequisites: 
* Python 3.9+
* pip
* MongoDB (local or cloud-based)
* LangChain
* OpenAI API Key (or any other LLM provider compatible with LangChain)

### Installation
```bash
pip install -r requirements.txt
```

Or install key dependencies manually:
```bash
pip install openai pymongo langchain gradio python-dotenv
```

### Setup
Create a `.env` file in your root directory and add:
```
OPENAI_API_KEY=your-api-key
MONGO_URI=your-mongo-uri
```

### Run the Project
Run the main script:

```bash
python Philosophy_Debater.py
```

Or open the notebook `Langchain_Mongo_Philosophy.ipynb` to run it step-by-step.

## File Structure

```
Intro_to_AI_FinalPJ/
├── Data/
│   ├── Aristotle/
│   │   ├── PhysicsI.txt
│   │   ├── PhysicsII.txt
│   │   ├── PhysicsIII.txt
│   │   ├── Nicomachean_EthicsI.txt
│   │   ├── Nicomachean_EthicsX.txt
│   │   ├── MetaphysicsI.txt
│   │   ├── MetaphysicsXII.txt
│   │   ├── On_the_SoulII.txt
│   │   ├── On_the_SoulIII.txt
│   └── Nietzsche/
│       ├── Beyond_Good_and_Evil.txt
│       ├── Human_All_Too_Human.txt
│       └── The_Joyful_Wisdom.txt
├── Philosophy_Debater.py
├── Langchain_Mongo_Philosophy.ipynb
└── README.md
```

## Analysis

Our approach involved retrieval-augmented generation (RAG) using LangChain. Here's how we conducted our analysis:

 * Text Processing: Used LangChain PDF loaders and recursive character splitters to divide texts into segments.
 * Embedding: Applied OpenAI’s embedding model to convert segments into vector format.
 * Storage & Retrieval: Stored vectors in MongoDB Atlas using the AtlasVectorSearch module for similarity-based search.
 * AI Simulation: Retrieved relevant text segments and prompted OpenAI’s LLM to generate philosopher-style responses.

## Results

Our system successfully simulates dialogue between philosophers based on their texts.
For instance, on the question “What is love?”, Aristotle emphasizes virtue and growth, while Nietzsche focuses on power and emotion.
This comparative approach reveals how different traditions respond to the same core ideas.

Limitations:
 * The dataset size was limited; broader coverage could improve depth.
 * Prompts sometimes led to repetitive or awkward language.
 * AI responses could benefit from more naturalistic dialogue formatting.

## Future Improvements
After finishing the prototype, we think it's a success regarding how it could provoke thinking and would deeply mimic the philosopher's thinking and wordings. However, for future improvements, it would definitely be more helpful with more dataset regarding our datasize was relatively small. On the other hand, it would also worth doing research on how to set the prompt to let the two debater talks more naturally, avoiding repeated wordings and awkward communication style. We hope it could be like two friends chatting and debating normally in daily life, which would also be easier for users to understand. 

In the future, we hope this tool can grow into a helpful assistant that presents different viewpoints and helps users understand what different people care about. By building custom databases for specific topics or viewpoints, it could become much more focused and useful than general-purpose AI. Instead of giving broad or vague answers, it could offer deeper, more relevant insights based on expert knowledge or specific perspectives. The debate mode can encourage users to see issues from multiple sides, sparking new ideas and helping them think more critically about their choices. This interactive format makes exploring complex topics more engaging and thought-provoking. 

## Contributors

Ivy (盧家愛, 113zu1055)   
Yoyo (陳玟佑, 113zu1017)   
Melisa (陳雨柔, 112zu1048)   
Yvonne (曾秭翊, 112zu1017)   

## Acknowledgments

We’d like to thank:

Prof. Pien, for their guidance throughout the course  
Our Teaching Assistance Harry for helping us troubleshoot technical issues and offering valuable feedback throughout the project  
The LangChain community, for making RAG pipelines accessible  
The Internet Classics Archive (MIT), for providing open-access philosophical texts  
Reddit Philosophy Community, for recommendations on core philosophical texts  
We also appreciate the open-source tools provided by LangChain, OpenAI, MongoDB Atlas, and Gradio.

## References

The Internet Classics Archive. https://classics.mit.edu/index.html   
LangChain Documentation. https://docs.langchain.com/   
Nietzsche, F. (Beyond Good and Evil, Human, All Too Human, and the Joyful Wisdom)   
Aristotle (PhysicsI ~ III, Nicomachean Ethics I & X, Metaphysics I & XII, On the Soul II & III. )   
MongoDB Documentation. https://www.mongodb.com/docs/   
OpenAI GPT API. https://platform.openai.com/  
Gradio Interface https://www.gradio.app/
