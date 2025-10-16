# aineshdas1-langgraph-mat496
Module 1 Video 1 
Introduction to LangGraph and Control Flow

What I Learned:
I learned that one language model alone is limited because it cannot use tools or handle many steps at once. To fix this, we use chains made of small steps before and after the model. A router agent follows fixed steps, while a fully autonomous agent decides everything on its own. LangGraph helps keep the system steady even when the model has more control.

What I Changed:
No major changes. I only explored how control flow and agents work in LangGraph.

Module 1 video 2
What I Learned

In this lesson, I learned how to build a simple graph and understood the main parts of a LangGraph. I learned that normal edges connect nodes in order, while conditional edges connect nodes based on certain conditions. I also learned that the state is the object passed between nodes and edges in the graph.

What I Changed

I created a simple LangGraph that checks the weather. Based on the condition, it gives a response depending on whether the weather is good or bad.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-1/simple-graph.ipynb

Module 1 video 3

What I learned:

I learned about LangGraph Studio, which is an interactive tool for building, viewing, and debugging AI agent workflows created with LangGraph. It works with LangSmith so we can trace, test, and optimize prompts or graph runs in real time. I also learned that each module has a studio directory to help run the LangGraph Studio for that module.

What I Changed:

Since there was no notebook for this video, I followed the tutorial, ran LangGraph Studio on my laptop, and tested a few graph states. It worked as expected

![Screenshot 2025-10-16 024922](https://github.com/user-attachments/assets/18ce110c-af80-45ae-998b-7b5667979d3e)


Module 1 video 4

Using Chat Messages and Tools in LangGraph

What I learned:
I learned how to use chat messages as the state in a LangGraph, how to bind a simple tool (like a weather function) to a chat model, and how the model can call that tool automatically based on user input. I also learned how to build a graph with nodes that process messages and append responses using a reducer.

Changes I made:
I created a small graph where a user can ask for the weather in a city. The graph node calls a chat model with a bound weather tool. I tested it with a human message asking about Delhi, and the model returned the appropriate weather response, which is appended to the messages state.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-1/chain.ipynb

Module 1 video 5

Routers and Conditional Tool Calls

What I learned:
I learned how to extend a LangGraph to act like a router. The chat model can now decide whether to return a natural language response or call a tool based on the user input. Conditional edges allow the graph to route automatically depending on the model’s output.

Changes I made:
I implemented a simple router graph that uses messages as state. It calls a tool when needed and otherwise returns a natural language response. I used:

-A ToolNode for calling the multiply tool.

-tools_condition as a conditional edge to route based on whether the output was a tool call

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-1/router.ipynb

Module 1 video 6

Building a Generic Agent Architecture

In this lesson, I learned how to extend a simple router into a generic agent architecture using LangGraph. I understood how the model can decide whether to call a tool or respond directly, forming a loop between the assistant and the tools until the task is complete. This structure follows the ReAct framework—where the model reasons, acts using tools, and observes the results to decide the next step. I also learned how to visualize the entire graph using the Mermaid diagram feature to clearly see how the assistant and tools interact.

Changes I made:
I implemented the generic agent architecture using three arithmetic tools—add, multiply, and divide—and connected them in a loop with the assistant node. I then tested it by asking a math question and verified that the model correctly invoked the tools in sequence to produce the right answer.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-1/agent.ipynb

![Screenshot 2025-10-16 154418](https://github.com/user-attachments/assets/66f12cdb-3813-46f9-91ae-45fe5a0b752f)

