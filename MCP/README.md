# Model Context Protocol
MCP is an open protocol that allows AI models to securely and flexibly connect to tools, API's and other resources. That means giving your LLM universal remote control to access and interact with the external services.

# What does it enable?
You can build AI Agents, don't just respond to queries, but take meaningful action like booking flights, checking the weather, or analyzing a spreadsheet, anything your application needs, all through one consistent interface. 

If you want to build AI-powered products that are more useful, more reliable, and more secure - you need a way to manage how models access tools and data. Here, MCP is becoming the emerging standard for that.

## Explain MCP
**Model:** could be any LLM such as GPT, Claude, Gemini, etc.

**Context:** means any extra information we give the model to help it make better decisions.

**Protocol:** means a set of rules, like how information should flow across the internet. Example: how HTTP works on top of TCP (Transmission Control Protocol). In MCP, it refers to the rules, how the model should receive unused context.  

## Limitations MCP SOLVES

1) **Problem 1 -- LLMs don't know recent stuff**
   Even if a model is trained every day -- which is rare -- it still won't know what happened today. Most models    are only updated once or twice a year.

2) **Problem 2 -- Context is expensive**
   Let's say " what happened in my city today?"

   At first, I have to feed in all the news data--- this is expensive process.

   LLM pricing is based on how much input/output(tokens) you give it.

Here comes MCP, which solves these problems by standardizing how to give context to models          efficiently and programmatically.


**Think of MCP like a USB-C port for AI applications. Just as USB-C provides a standardized way to connect electronic devices, MCP provides a standardized way to connect AI applications to external systems.**

# What can MCP enable?
* Agents can access your Google Calendar and Notion, acting as a more personalized AI assistant.
* Claude Code can generate an entire web app using a Figma design.
* Enterprise chatbots can connect to multiple databases across an organization, empowering users to analyze data using chat.
* AI models can create 3D designs on Blender and print them out using a 3D printer.
​
# Why does MCP matter?
* Depending on where you sit in the ecosystem, MCP can have a range of benefits.
* **Developers:** MCP reduces development time and complexity when building, or integrating with, an AI application or agent.
* **AI applications or agents:** MCP provides access to an ecosystem of data sources, tools and apps which will enhance capabilities and improve the end-user experience.
* **End-users:** MCP results in more capable AI applications or agents which can access your data and take actions on your behalf when necessary.

## Concepts of MCP
​
## Participants

MCP follows a client-server architecture where an MCP host — an AI application like Claude Code or Claude Desktop — establishes connections to one or more MCP servers. The MCP host accomplishes this by creating one MCP client for each MCP server. Each MCP client maintains a dedicated one-to-one connection with its corresponding MCP server.


## Simple Term Explanation 

* (MCP follows a client-server architecture. Here is what it means: if you are using the HOST LLM app like an IDE, Claude, MCP CLIENTS reside inside the HOST app, you can connect to one or more MCP SERVERS to CLIENTS. )

* (Lets say you have multiple files locally stored or some data available in the internet(Database), now i want my MCP CLIENT inside my HOST app to chat with this data source -- meaning it should be able to fetch and interact with that information, but, by default HOST App doesnt have access for that, to enable this i can create an MCP SERVER and connect to the HOST. This MCP SERVER knows how to fetch and read data from the DATABASE or INTERNET, and more importantly, it knows how to package that information as context and send it Model running inside the HOST APP. The great part is I'm not limited to just one MCP SERVER; I can create multiple MCP SERVERS, each connected to different data or tools. )

* ( We can connect one MCP SERVER to get weather updates, another one that reads local files data, another one that performs GOOGLE searches, another one that fetches data from private APIs. Once created, I can register all these MCP SERVERS to my MCP CLIENT. This setup lets the HOST APP interact with the external world in a smart and efficient way. Each MCP SERVER brings in just the right amount of context needed without overloading the model.)

----- *THIS IS WHAT AN MCP SERVER DOES* ----

* **MCP SERVERS acts as a bridge between the external data and models context window.**


# The key participants in the MCP architecture are:
* **MCP Host(IDE, Claude):** The AI application that coordinates and manages one or multiple MCP clients
* **MCP Client:** A component that maintains a connection to an MCP server and obtains context from an MCP server for the MCP host to use
* **MCP Server:** A program that provides context to MCP clients
  
**For example:** Visual Studio Code acts as an MCP host. When Visual Studio Code establishes a connection to an MCP server, such as the Sentry MCP server, the Visual Studio Code runtime instantiates an MCP client object that maintains the connection to the Sentry MCP server. When Visual Studio Code subsequently connects to another MCP server, such as the local filesystem server, the Visual Studio Code runtime instantiates an additional MCP client object to maintain this connection, hence maintaining a one-to-one relationship of MCP clients to MCP servers.



# MCO CORE COMPONENTS 

MCP is the new standard for building APIs --- and it works very differently from traditional ones.

**BEFORE CREATING A SERVER WE SHOULD KNOW ABOUT MCP SERVER PRIMITIVES**


*If we look at MCP architecture, HOSTs are LLM-powered apps like Claude or IDE, and MCP CLIENTS live inside the HOST APP and talk one-to-one with SERVERS. SERVERS provide TOOLS, RESOURCES, and PROMTS ie, CONTEXT. And all this communication happens over a TRANSPORT LAYER*


*For MCP SERVER development, we need to know about 3 important primitives in MCP:*

* **Resources:** provide static or dynamic data as context. It is similar to an HTTP GET request, which is they performs *read-only* operations. 
* **Tools:** perform actions like sending data, updating systems. They are similar to HTTP POST requests, that is, they perform *write and update* operations.
* **Prompts:** are reusable prompt templates. They can accept dynamic input, including resource context, chain multiple steps, and guide workflows. 
  
   
# HOW MCP CLIENT AND SERVER TALK?

There are 2 built-in MCP transports:

1) STDIO: Uses standard input/output streams for direct process communication between local processes on the same machine, providing optimal performance with no network overhead.
2) Streamable HTTP (SSE): Uses HTTP POST for client-to-server messages with optional Server-Sent Events for streaming capabilities. This transport enables remote server communication and supports standard HTTP authentication methods including bearer tokens, API keys, and custom headers. MCP recommends using OAuth to obtain authentication tokens.



