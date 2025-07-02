# Rule-Based-Chat-Bot

A fun little personal project where I created a Spring Boot rule-based chatbot that:

-has the capability to chat within parameters and return results

-has the capability to provide information about a country’s capital and national animal and flower 

-has the ability to remember which country has been selected during a chat for further information and

-will provide a web-based interface for the user to interact with the rule-based chatbot engine via any modern desktop browser.



To run the chatbot:
download the files and run ChatbotApplication.java
go to http://localhost:8080/ and start interacting with the chat bot!


The starter code is arranged as follows:

The core or base package is com.ajsd.chatbot.

The packages and classes inside the core or base package are:

The package for the model classes is com.ajsd.chatbot.model, and it contains: 

ConversationContext, which is used to store the current step of communication, selected countries being discussed, and available options. 

CountryInfo, which is used to store information about a country. It is used to associate a country's name with the capital, nationalAnimal, and nationalFlower.

The package for configuration classes is com.ajsd.chatbot.config, and it contains:

CountryDataLoader, which is used to load the information about the countries from the JSON file named countries_data.json in the resources folder of the Spring Boot application. This class also provides methods to access data that is used by the service, storing the data in a HashMap.

The package for the service classes is com.ajsd.chatbot.service, and it contains: 

ChatbotService, which utilizes the CountryDataLoader class to access the data of the different countries and provides access to the data via this Service class. 

RuleBasedEngine is the class at the heart of the rules of the Chatbot. It contains the logic to return the appropriate response to the user and remembers the context by leveraging the ConversationContext class object, which is passed to it by the controller. 

The package for the controller classes is com.ajsd.chatbot.controller, and it contains: 

HomeController, a controller class with only one endpoint “/,” returns the thymeleaf template index.html.

ChatbotController, which is the controller responsible for all the communication between the web-based interface and the RuleBasedEngine class. It utilizes a session-based reference to an object of the ConversationContext class so that each session communication, like the country being discussed, is remembered. This controller class has a single endpoint, “/chat,” responding to the HTTP verb type POST.  

The class inside the core or base package is ChatbotApplication, which is the starting point containing the main method of the Spring Boot Application.
