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

Module 1 video 7

Agent with Memory

What I learned:
I learned how to add simple memory to a LangGraph agent. The agent can call tools to store and retrieve user preferences, then use those stored values later in the conversation. This creates a loop where the assistant acts, observes tool results, and reasons about the next step.

What I changed:
I built a small agent that stores preferences in a local memory store with two tools (set_pref and get_pref). I tested asking the agent to remember a favorite color and later to recall it. I also visualized the graph to confirm the assistant-to-tools loop works as expected.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-1/agent-memory.ipynb

![Screenshot 2025-10-16 171627](https://github.com/user-attachments/assets/1b22e172-9b6b-442a-8907-f0a94d663fb0)



Module 2 video 1 

What I learned:
In this part, I learned how to define a custom state schema using the pydantic.BaseModel. The schema helps structure data as it passes through nodes in the graph. Each node updates or modifies parts of the state, making it easier to manage complex workflows.

What I changed:
I created a simple weather information flow where one node fetches the weather details and another displays it. The state schema (WeatherState) keeps track of the city, temperature, and weather status throughout the process.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-2/state-schema.ipynb

Module 2 video 2 

What I learned: In this notebook, I learned about state reducers, which allow multiple updates to be merged into a single state. Reducers are helpful when different nodes modify parts of the same state in sequence. 

What I changed: I created a shopping flow example where items are added to a cart from different nodes — fruits and vegetables — before finally displaying the full cart at checkout. The reducer function add_item() helped update the shared cart state effectively.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-2/state-reducers.ipynb


Module 2 video 3

What I learned
I learned how to define typed schemas (TypedDicts) for overall and private state, how to declare a StateGraph with input and output schemas, and how to connect nodes that transform parts of the graph state.

What I changed
I adapted the example to show a thinking_node (simulating an intermediate private state) and an answer_node that builds a simple deterministic answer. I added a compact invocation so the output is clear.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-2/multiple-schemas.ipynb


Module 2 video 4

What I Learned

I learned how to create a simple LangGraph chatbot using nodes and edges, and how to manage long conversations by trimming messages so the model sees only the most recent context. I also understood the difference between filtering and trimming messages.

What I Changed

I used a new conversation about planning a trip to Japan and implemented trimming based on the last four messages before sending them to the model. Now, it focuses on what was said recently without getting confused by the older messages

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-2/trim-filter-messages.ipynb

![Screenshot 2025-10-23 014006](https://github.com/user-attachments/assets/8e517822-7e8c-46e6-a81d-9b0ca9c94681)


Module 2 video 5

What I learned
I learned how to create a simple LangGraph that summarizes an entire chat conversation. I understood how to define a MessagesState, add a summarization node, connect the nodes, and invoke the graph to produce a summary using an LLM.

What I changed
I changed the example conversation to one related to my own chatbot project. I used the same summarization node logic from the notebook to generate a short summary of my custom messages.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-2/chatbot-summarization.ipynb

![Screenshot 2025-10-23 015011](https://github.com/user-attachments/assets/03f9aca0-a71c-425c-8c2e-1c13084f0afb)


Module 2 video 6

What I Learned

I learned how to create a LangGraph chatbot that can summarize conversations and remember previous messages using an external database. I also learned how to keep a running summary and selectively store only recent messages to manage memory.

What I Changed

I used a new conversation scenario where the chatbot remembers personal details and answers questions about them. I implemented summarization after more than six messages and used Sqlite to store the conversation so it can persist even if the notebook is restarted.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-2/chatbot-external-memory.ipynb



Module 3 Video 1

Streaming and Interruption

What I learned:
I learned how streaming works in LangGraph using a ChatOpenAI model. The model can return responses in small chunks instead of one long message, just like a live typing effect. I also learned that the stream can be interrupted anytime, which is helpful for interactive applications.

What I changed:
I created a simple streaming node that prints tokens as they are generated by the model. I tested it by asking a question and watching the model stream its reply live.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-3/streaming-interruption.ipynb

![Screenshot 2025-10-27 025823](https://github.com/user-attachments/assets/e0de27c2-2569-45ec-a8c5-a2ab50f7a3b1)


Module 3 video 2

Breakpoints

What I learned:
I learned how to pause execution using breakpoints inside LangGraph workflows. This helps inspect or debug what’s happening inside a node before continuing.

What I changed:
I added a simple breakpoint using input() that pauses before the model’s response. This shows how developers can stop the flow, check values, and then resume.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-3/breakpoints.ipynb

![Screenshot 2025-10-27 030739](https://github.com/user-attachments/assets/2f05e6b1-a290-4afb-94cf-c08887e08761)



Module 3 video 3

Edit State and Human Feedback

What I learned:
I learned how human feedback can be used to edit or modify the state of a LangGraph workflow. It allows updating the model’s response based on user corrections, making the graph more interactive and adaptable.

What I changed:
I created a simple feedback node that lets me modify the AI’s reply manually after seeing it. If I say “yes,” it takes a new correction and updates the message before saving it.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-3/edit-state-human-feedback.ipynb

![Screenshot 2025-10-27 031345](https://github.com/user-attachments/assets/ba8e173c-d4f5-4894-bc02-333131834682)


![Screenshot 2025-10-27 032622](https://github.com/user-attachments/assets/c9661dde-0201-4a8c-8bef-cdb49b3e905f)


Module 3 video 4

What I learned:
I learned how dynamic breakpoints allow the chatbot to follow different paths depending on the conversation. The graph can automatically decide which node to go to next, making the flow feel more natural and context-aware.

What I changed:
I made my own example that switches between a food chat and a travel chat depending on the topic. It helped me understand how to use conditional edges to control the conversation flow.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-3/dynamic-breakpoints.ipynb

![Screenshot 2025-10-27 045101](https://github.com/user-attachments/assets/56a39bba-d4af-431b-9040-cf9c20556121)



Moule 3 video 5

What I learned:
I learned how “time travel” lets me look back at earlier conversation states. It helps in reusing or summarizing past messages so the chatbot can recall context when needed.

What I changed:
I created an example that summarizes older messages about Mars before ending the chat. This helped me understand how to access and process past conversation history inside a node.

notebook link: https://github.com/aineshdas1/aineshdas1-langgraph-mat496/blob/main/module-3/time-travel.ipynb

![Screenshot 2025-10-27 135533](https://github.com/user-attachments/assets/5ef61ff4-0d5b-4e75-90d0-c78047cd511c)

![Screenshot 2025-10-27 135602](https://github.com/user-attachments/assets/336beb4a-7515-45b5-97b2-07328f3719d4)






