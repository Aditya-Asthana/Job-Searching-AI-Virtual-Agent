# Job-Searching-AI-Virtual-Agent

Job Searching AI Virtual Agent Documentation:
(Note – We pivoted from making a job-searching application for users, to a recruiter-based application to find candidates for the job they are looking for. Most of the architecture stayed the same. We did this for two reasons. First, we identified there are many AI-based job searchers already available. Secondly, we believe this modification is a unique idea that can be refined to implement in the industry.)
Textdata Link: https://textdata.org/submissions/6725088c22ea54f14be31ff0

Code Documentation:
1.	Data – Utilized 25 resumes to create embeddings for this project, fabricated using ChatGPT model GPT4o. This data was formatted as JSON files to easily retrieve fields out from each resume. In the future, there would be a way to add a function so that users can upload their resumes, and a function would convert it to JSON. Then it would be uploaded to the data file to be used for embeddings.
2.	Data Processing – Parses candidate resumes stored as JSON files into structured text to extract key details like Skills, Education, Experience, and Projects. Then, splits the structured text into smaller chunks using CharacterTextSplitter to enable embedding generation.
3.	Vector Database Ingestion – Converts processed text chunks into vector embeddings using OpenAI's text-embedding-ada-002 model. Next, stores these embeddings in a persistent ChromaDB directory for efficient retrieval during queries.
4.	LLM – Creates a retriever from the ChromaDB vector store to find the most relevant resume chunks for a query. After, uses a RetrievalQA chain with OpenAI's GPT-4 model to process retrieved data and generate accurate, context-aware responses to user queries.
5.	Built-in UI – Implements a command-line interface for recruiters to interactively query the candidate database and receive AI-generated answers. Finally, builds a graphical user interface using ipywidgets. This features a text input box, a send button, and an output area to display conversations. In the future, this would be a full-stack application with dedicated data storage.

TextData Details:

Project Title: Job Matching Chatbot

Team Members (Names and netID of all members): Aditya Asthana, asthana6 Daniel Gregory, dg42 Gunjan Jain, gunjanj2 Samir Gray, sbgray2

Project Coordinator (Name and NetID): Aditya Asthana, asthana6

Project Keywords: #JobMatching, #IntelligentTaskAgent, #NLP, #LLM, #RAG, #VectorDatabase

Project Description (Write ~200 words describing the problem, your high-level approach, and how you plan to evaluate / demonstrate effectiveness of your approach):

The goal of this project is to develop an intelligent task agent (Task 3) to make job searching easier. Typical job search engines often return results that require extensive filtering and can lead to frustration for applicants when they find themselves applying to roles they don’t fully qualify for or are overqualified for. Clearly, the current process for job recruitment is incredibly time-consuming and overcomplicated. Our project will address this by automating these job application processes and enhance the applicant’s resume to be selected for opportunities. At a high level, there are three main technologies that will be used to construct this chatbot. First, we will utilize a vector database to effectively store users’ resumes and create embeddings. Next, we will use retrieval augmented generation to have job specific data that will be able to provide more accurate responses to the user. Finally, we will use a large language model as the main “engine” of the chatbot which will allow the user to have a flowing and interactive conversation. To measure the success of this approach, we can look at two metrics. First we can track the success of how often the chatbot accurately identifies a correct opportunity for a user. Additionally, we can use a F1 score to see the effectiveness of the LLM with nuanced questions.

Current Progress: At this stage of the project we have set up a vector database known as Milvus. We chose this vector database mainly because it is open source and performs high-speed searches on data. The large language model we are implementing will be llama-3b (this model might change) mainly because it is open source and generally provides good test answers.

Next Steps: We need to integrate the vector database and the Large Language model together. To do this, we plan on using Langchain to create actions. Beyond this, we need to make a functional chat assistant which is prompted correctly. Maybe, it could be useful to use a fin-tuned model for better results but it depends on the final output.

Challenges: The main challenge we are facing is obtaining data. To create an effective RAG system, we need lots of resume to create embeddings for so that when a user uploads his resume, it can have an embedding close to it. One solution to this is to use generative AI to create resumes and classify them for what job they should be for.
