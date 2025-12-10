# Model Context Protocol
MCP is an open protocol that allows AI models to securely and flexibly connect to tools, API's and other resources. That means giving your LLM universal remote control to access and interact with the external services.

# What does it enable?
You can build AI Agents, don't just respond to queries, but take meaningful action like booking flights, checking the weather, or analyzing a spreadsheet, anything your application needs, all through one consistent interface. 

If you want to build AI-powered products that are more useful, more reliable, and more secure - you need a way to manage how models access tools and data. Here, MCP is becoming the emerging standard for that.

## Explain MCP
**Model:** could be any LLM such as GPT, Claude, Gemini, etc.

**Context:** means any extra information we give the model to help it make better decisions.

**Protocol:** means a set of rules, like how information should flow across the internet. Example: how HTTP works on top of TCP (Transmission Control Protocol). In MCP, it refers to the rules, how the model should receive unused context.  

## Limitations

1) **Problem 1 -- LLMs don't know recent stuff**
   Even if a model is trained every day -- which is rare -- it still won't know what happened today. Most models    are only updated once or twice a year.

2) **Problem 2 -- Context is expensive**
   lets say " what happened in my city today?"

