## TeachGPT
**Description:** The application of ChatGPT for the development of a wrapper API has increased its utility for educators and students within the education industry.

### Table of Contents

- [Project Goals](#project)
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

The code above is a Python function called get_param() that takes in user input as a parameter, and parses the input to extract relevant entities and set the temperature parameter for a chatbot.

The function first loads the en_core_web_md model from the spaCy library and defines a list of entities and punctuations to be removed from the input string. It then parses the input using the spaCy model and extracts entities from it. The function then removes punctuations from the input string and searches for entities in a predefined list. If an entity is found, it is added to a list of prompt characteristics.

Next, the function calculates the temperature value based on two types of parameters: grade level and level of difficulty. The grade level is identified based on a predefined list of grade levels, and a temperature value is calculated based on the identified grade level. The level of difficulty is identified based on a predefined list of difficulty levels and the prompt characteristics. The temperature value is adjusted based on the identified level of difficulty and the identified grade level. Finally, the function returns the temperature value.

Overall, this code aims to provide a method for automatically determining an appropriate temperature value for the chatGPT API based on user input.
