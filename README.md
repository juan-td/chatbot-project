# chatbot-project
A simple chatbot development based on techwithtim's tutorials and followed up with my own ideas
## intents.json
Describes various intents the user's message (greeting, goodbye, name, hours) based on a fictional cookie store. Every intent has it's own set of patterns (possible inputs which denote that intent) as well as a set of generic responses.
## chatbot_tutorial
Based on Tech with Tim's tutorial series (https://youtu.be/wypVcNIH6D4), model trained to classify the intent of a user's message. Words are stemmed using nltk, tokenized, and turned into one-hot vectors. A dense layer neural network with a softmax output predicts the intent, and a generic response is returned.

    Start talking with the bot! (type quit to stop)

    You: hello
    Chatbot: Good to see you again!
    You: what do you sell?
    Chatbot: Cookies are on the menu!
    You: what time do you open?
    Chatbot: Could you word that differently?
    You: quit
## chatbot_lstm
Similar to chatbot_tutorial this time using char level tokenization and an embedding layer followed by an LSTM layer. It shows greater toleance towards typos, user doesn't necessarily have to type the exact words included in the patterns, and has a better ability to recognize unknown inputs.

    Start talking with the bot! (type quit to stop)

    You: hello!
    Chatbot: Good to see you again!
    You: how are you?
    Chatbot: Good to see you again!
    You: what do you sell?
    Chatbot: We sell chocolate chip cookies for $2!
    You: do you have a name?
    Chatbot: I'm Chatbot!
    You: how old are you?
    Chatbot: I am 18 years old!
    You: do you deliver?
    Chatbot: Sure, call this number and make your delivery!
    You: hellwo!
    Chatbot: Hi there, how can I help?
    You: do u make reservation
    Chatbot: I dont understand
    You: do u accept reservation
    Chatbot: We'd gladly take your reservation, call this number
    You: wat is ur name
    Chatbot: I'm Chatbot!
    You: goodby chatbot!
    Chatbot: Goodbye!
    You: quit
