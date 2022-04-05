# ChatBot

## Description
This is a general-purpose ChatBot about retail clothing and accessories. ChatBot is able to discuss reviews, complaints, product satisfaction, and suggestions. The system has been equipped with a GUI for a cleaner interface and other new systems listed below.

## How to compile and run
Firstly download the repository. Then run the "Main.py" file.

<br><br/>

# Individual Assignment New Code Features
### API's:
- Wikipedia
- Google Translate

## Wikipedia API
I've incorporated the Wikipedia API into the chat bot to be able to handle generic questions. The previous iteration of this assignment had no capabilities to answer questions so this is quite an improvement. Once the chat bot identifies the prompt as a question, it will try to parse the subject from the sentence and retrieve a 1 sentence summary from the subject's wikipedia page. If the chat bot can't identify a subject or if the subject is too broad, it will ask the user to rephrase in a more specific manner.

(get it to be like "I would suggest a parka" and then be like "what is a parka" ... "what is a parka in terms of clothing" ...)

## Google Translate API
I have also implemented the googletrans API which uses data from Google Translate to support dialogue with the chat bot in any language. The user can ask the chat bot anything in their native language and will receive a response back in that same language. It works dynamically meaning that the user can switch between languages mid-conversation and the bot will be able to identify the new language and respond accordingly. As with most language software the translations aren't always perfect but it's sufficient for our chat bot.


<br><br/>
#
## Assignment 3 Code Features
### Brand-new GUI to interact with. (1 point)
- The new GUI allows the user to interact with the bot with a more user-friendly medium.

**example:**

![alt text](https://github.com/Team-22-COSC-310/ChatBot/blob/main/Assets/Images/GUI%20Example.png?raw=true)

###Extra Topics the bot can suggest other theatricals of clothing. (0.5 points)
- This helps the user better extrapolate their feelings towards the product and give the system usefully feedback.
    
**example:**

    User: Could you suggest a product for me?
    
    CostomerService: You should check out are shoes. Does this product interest you?

###5 responsible responses outside the two main topics. (0.5 points)
- The bot is able to understand its limitations and steer the conversation back to its understood topics.
    
**example:**

    Responses:
    "Ok"
    "Great!"
    "Is there anything else you would like to share?"
    "How else can I assist you today?"
    "I'm sorry I don't understand what you are asking me? Could you rephrase your question."
    "I can't understand what you said. could you try again."
    "Sorry I didn't quite get that. could you try again."
    "I couldn't quite understand what you were talking about."
    "I'm sorry that is beyond my understanding."

###Bot can handle spelling mistakes with Porter Stemmer. (1 point)
- This is done with Porter Stemmer and is better at normalizing responses i.e. given a wide response variation for a single response it's able to normalize the response to a single normalized one that can be interoperate the same no matter the variation of the response. This enables the bot to give a similar response every time.
- The bot also uses cosine similarity to determine user sentiment so if a word is misspelled it will not be critical the overall detection of the users' sentiment.

**example:** Porter Stemmer
  
    liked
    likely 
    liking
  
    All of these will be reduced to "like".

###Use of language toolkit: Named entity recognition (2 points)
- This is done with spaCy module in the response.py file to find products the user is talking about.

**example:**

    User: My shoes that I bought broke.
    
    CostumerService: Awesome! I am so glad you enjoyed your shoes. What was the best part about the shoes?

###The bot is able to have a conversation with another bot. (3 points)
- Using sockets or locally the bot is able to talk with another bot. This can give great insight into gaps in the bots' knowledge without human interaction.

**commands:**

    --local "Creates local enviroment for user and bot"
    --host <ip> <port> "Creates enviroment as host for other applications to join"
    --join <ip> <port> "Creates enviroment as client to join the host application"

**example:**

    Bot_1: Hello!
    Bot_2: Howdy! I am here for any input on are products you have!
    Bot_1: I am sorry to hear about that. What in particular was wrong with the product?
    Bot_2: Thank you for sharing your complaint about are product. Is there anything we could do in the future to prevent this?
  
    As you can see testing are bot against its self yield mixed results since it's only oriented to customer responses and not giving complaints, reviews or satisfaction. But against a bot that was it would return the proper results.
