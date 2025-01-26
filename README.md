import nltk
from nltk.chat.util import Chat, reflections

# Define pairs of patterns and responses
pairs = [
    (r"hi|hello|hey", ["Hello, how can I assist you today?", "Hi there!"]),
    (r"what is your name?", ["I'm a chatbot created to assist you."]),
    (r"how are you?", ["I'm doing great! How about you?", "I'm just a program, but thanks for asking!"]),
    (r"(.*) your (.*)?", ["Why do you ask about my %2?", "That's an interesting question about my %2!"]),
    (r"quit", ["Goodbye! Have a nice day!"]),
    (r"(.*)", ["I'm sorry, I don't understand. Can you please rephrase?"])
]
# Create a chatbot using the defined pairs and reflections
chatbot = Chat(pairs, reflections)
# Start the conversation
def chat():
    print("Hi, I'm your chatbot! Type 'quit' to exit.")
    while True:
        user_input = input("You: ")
        if user_input.lower() == "quit":
            print("Chatbot: Goodbye!")
            break
        response = chatbot.respond(user_input)
        print("Chatbot:", response)
# Run the chatbot
chat()
