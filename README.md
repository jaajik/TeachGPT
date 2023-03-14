## TeachGPT
**Description:** The application of ChatGPT for the development of a wrapper API to increase its utility for educators and students within the education industry.

### Table of Contents

- [Project Goals](#project)
- [Features and Parameters of ChatGPT](#features)
- [Libraries Used](#libraries)
- [Features](#features)
- [Credits](#credits)

### Project Goals

The project is divided into two main phases, each involving specific tasks and objectives:

_Phase #1:_

1. Utilize the ChatGPT API within Jupyter Notebook to create a chatbot that can interact with users.
2. Use Gradio to develop a web application that allows users to interact with the chatbot.
3. Implement NLP techniques to parse user input and extract entities to improve the chatbot's response accuracy.
4. Acquire a comprehensive understanding of ChatGPT parameters to enable better chatbot performance.
5. Calculate ChatGPT temperature parameter based on user input for more precise responses.

_Phase #2:_

1. Perform in-depth NLP analysis to enhance the chatbot's ability to parse user input.
2. Create a web application using Streamlit to provide an improved user experience.
3. Implement prompt engineering techniques to improve the chatbot's natural language generation capabilities.

> The project team will allocate appropriate resources to each phase and task in order to achieve project objectives in a timely and effective manner.

> This repository provides an overview of Phase #1 of the entire project.

### Features and Parameters of ChatGPT
https://docs.google.com/document/d/1J5PkzR6e1R0jPNTvXN1PG-KUpRoAkSPQ4Sq3ISKSVrA/edit

What is ChatGPT? 
- It is a conversational AI that is capable of learning from its own mistakes. 
- It interacts in a user-friendly text mechanism - essentially very easy to use. 

#### Applications

1. Answers: answers any questions about facts, existing knowledge and even about code
    
    - Ex: Q&A, code conversion to different langauges, factual answering, tutoring, etc.
2. Classification: creates categories based on what is asked
    
    - Ex: types of memory (education), keywords (essays), detection (any text)
3. Code: refers to all programming languages and solves various problems
    
    --> Capable of debugging, fixing errors, translating between languages, creating code etc. 
4. Conversation: a conversational bot
    
    - Ex: answers questions, develops solutions to everyday problems
5. Generation: generates given task into requested formatting
    
    - Ex: summarizing content for a second grader, language translation, parsing, etc
6. Translation: restricted to coding to speaking languages
7. Transformation: completes any given command for conversions 
    
    --> can be mathematical or literary such as horror
    
#### Application Parameters and Attributes

| Parameters | Description | Range (*if applicable*) | Specification |
| --- | --- | --- | --- |
| Mode | Will modify text or answer provided commands in textbox based on type of mode. | N/A | Three Types: Complete, Insert, Edit | 
| Model | Various models are provided to complete certain functions such as generate natural language or code or to fine tune a model to find sensitive or unsafe text | ** depends on model | Each model has different pricing based on complexity and has limited tokens | 
| Temperature | Determines the deterministic capabilities of provided text - response prompt may vary regardless of  consistency in variables | 0-1 | 0 = very deterministic (small amount of variability - see repetitiveness) 1 = non-deterministic (shows various options and high variability) | 
| Max Length | Represents the maximum number of tokens available for user to apply in textbox | <= 4000 tokens | ** each application example has various token length - 1 token = 4 letters |
| Stop Sequences | “stop”; indicates that the model is sufficient with good quality for completion - will stop generating sequence/further tokens | 0-4 | Returned text will not contain stop sequence nor the text after |
| Top P | Control diversity in solutions/results choosing smallest number of words based on cumulative probability exceeding p (nucleus sampling) | 0-1 | 0 = least amount of variability is taken into consideration 1 = all options are weighed in and considered into the result | 
| Frequency Penalty | Decreases model’s likelihood of text repetition of similar verbatim in text. Specifically determines the penalty of frequency in text. | 0-2 | 
| Presence Penalty | Penalizes new tokens on frequency of repetitive text + increases model likelihood to talk about new topics. | 0-2 |
| Best Of | Generates multiple completions of given task and displays only the best; uses up tokens easily | 1-20 | ** only works when set to 1 |
| Inject Start Text | Provided user text to add after user’s input when generating a response. | N/A | 
| Inject Restart Text | Provided user text to add after the model's generation to continue the given pattern. | N/A | 
| Show Probabilities | Highlights the likeliness of a token to be generated - aids in debugging and seeing alternative options for generated token | N/A | 4 options: Off, Least Likely, Most Likely, Full Spectrum | 
| Codex Model | Generates code to given response | ** available in multiple coding languages dependent of accessibility (premium or normal) | ONLY IN PROGRAMMING BASED APPLICATION EXAMPLES |

### Libraries Used

**OpenAi**
--> An OpenAI key was utilized to generate an environment variable that facilitated the opening of a testing site, which was instrumental in assessing the relationship between user interaction and the bot's performance.

**Gradio**
--> Gradio was employed to automatically generate a public link that grants access to the mentioned environment above.

**Spacy**
--> The Spacy framework played a crucial role in the development of the get_param() method, primarily by facilitating the conversion of user input into a comprehensible format for iteration. Additionally, Spacy was utilized to iterate through each of the input entities as demonstrated.

**RapidFuzz**
--> RapidFuzz was instrumental in the construction of the get_param() method and played a significant role in the iteration through user input within the environment key. 

### Features

***get_param():***

The code provided in the trials jupyter file is a Python function called get_param() that takes in user input as a parameter, and parses the input to extract relevant entities and set the temperature parameter for a chatbot.

The function first loads the en_core_web_md model from the Spacy library and defines a list of entities and punctuations to be removed from the input string. It then parses the input using the Spacy model and extracts entities from it. The function then removes punctuations from the input string and searches for entities in a predefined list to ensure maximum ability of the function to identify specific characteristics with interacting with the bot. If an entity is found, it is added to a list of prompt characteristics.

The temperature parameter is then calculated based on two different types of parameters: grade level and level of difficulty. If no grade level nor level of difficulty was stated in the provided user input, the default temperature value was set to an average of 0.5. If they are, then the identified grade level is compared to a predefined list of grade levels, and a temperature value is assigned based on the position of the identified grade level in the list. The temperature value was exponentially adjusted based on the specified grade level. This was due to the inverse relationship between grade difficulty and the required variability for higher accuracy. 
The level of difficulty is also determined based on the identified entities and a list of predefined difficulty levels through the use of a nested for loop, with a temperature value assigned based on the position of the identified level in the list. Using fuzz.ratio, we compared the user input entities identified by the bot with the prompt_characteristics, to see if the identified level was accurate and then set to the temperature variable (delta_temp) to the position of the levelFinally, the temperature values for grade level and difficulty are adjusted based on certain delta values, and a final temperature value is returned.

Overall, this code aims to provide a method for automatically determining an appropriate temperature value for the chatGPT API based on user input.
