## Topic: Building a Trello AI Agent with LangChain

---

# 1. Start with the Problem

## Main Notes

Today, there are many tutorials on the internet that teach isolated pieces. Some focus only on building AI agents. Others focus only on developing full-stack applications. But in real projects, the real business value does not come from learning these pieces separately.

The real business value lies in integrating AI into software systems and building AI-driven software systems that can understand user intent and act inside real business applications.

In this session, we will understand that integration through a small Trello demo. Trello is a widely used project management software, so it gives us a practical example of how AI can work with a real software platform.

In simple words:

- A Large Language Model can **think in language**
- An AI-driven software system can **understand, decide, and act through software tools**

## Speaker Notes

> <mark><em>Let me begin with a shift in perspective. Today, there are many tutorials available on the internet. Some teach only how to build an <strong>AI agent</strong>. Others teach only how to build a <strong>full-stack application</strong>. But in real projects, the actual business value does not come from learning these parts separately.</em></mark>
>
> <mark><em>The real value comes from <strong>integrating AI into software systems</strong> and building <strong>AI-driven software systems</strong> that can understand user intent and work with real business applications.</em></mark>
>
> <mark><em>So in this session, I am not only showing an isolated agent example. I am using a small <strong>Trello</strong> demo to show how AI, software tools, and a real application can work together in one practical flow.</em></mark>
>
> <mark><em>This is the central idea of the session: not just building an agent, but understanding how an <strong>AI system works inside a software system</strong>.</em></mark>

---

# 2. What is a Large Language Model

## Main Notes

A Large Language Model is fundamentally a text prediction and generation system.

It is very good at:

- understanding instructions
- generating human-like responses
- summarizing text
- explaining concepts
- answering questions

But by default, it does **not** have direct access to external systems such as:

- Trello
- email
- databases
- APIs
- file systems

So if I ask a plain Large Language Model to create a Trello card, it may tell me the steps, but it cannot actually create the card unless we give it a controlled way to perform that action.

That is where tools come in.

## Speaker Notes

> <mark><em>A simple way to understand a <strong>Large Language Model</strong> is that it is a very advanced text engine. It predicts and generates language extremely well.</em></mark>
>
> <mark><em>It can explain, summarize, answer, and guide. But one thing to remember is that it does not automatically have access to external systems. It does not inherently have permission or capability to go and create a <strong>Trello card</strong>, send an email, or update a database.</em></mark>
>
> <mark><em>So the model has intelligence in language, but not execution power over business systems unless we explicitly connect that capability.</em></mark>

---

# 3. What is a Tool

## Main Notes

A tool is a callable function or capability that allows the model to interact with the outside world.

In our Trello example, a tool could be:

- get Trello lists
- create a card
- move a card
- update a card description
- fetch cards from a list

So the Large Language Model provides the intelligence to understand the request, while the tool provides the execution capability.

**The model understands the intent, and the tool performs the action.**

## Speaker Notes

> <mark><em>Now we come to the most important bridge between language intelligence and real action, and that is the <strong>tool</strong>.</em></mark>
>
> <mark><em>A tool is simply a function or callable capability that the model can use. In our <strong>Trello</strong> use case, a tool could fetch lists, create a card, move a card, or update a description.</em></mark>
>
> <mark><em>So I often explain it like this: the model is the brain for interpretation, and the tool is the hand for execution.</em></mark>
>
> <mark><em>This distinction is important in enterprise systems because we usually do not want the model to directly and freely do anything. We want it to act only through controlled <strong>tools</strong> that we define.</em></mark>

---

# 4. What is an AI Agent

## Main Notes

An AI agent is a system where a Large Language Model is combined with tools, instructions, and control logic so that it can take actions toward a goal instead of only generating text.

A typical agent works like this:

1. It receives a user goal
2. It understands the intent
3. It decides whether a tool is needed
4. It calls the appropriate tool
5. It observes the result
6. It either continues or returns the final answer

So the main difference is:

- A plain Large Language Model gives responses
- An agent can decide and act

## Speaker Notes

> <mark><em>Once we combine the model with <strong>tools</strong> and some control logic, we move from a simple text generator toward an <strong>agent</strong>.</em></mark>
>
> <mark><em>An agent is goal-oriented. It receives a user request, understands what is being asked, checks whether an action is needed, uses the right tool, observes the result, and then either continues or finishes.</em></mark>
>
> <mark><em>So the main difference is very practical. A plain model can answer. An <strong>agent</strong> can answer and act.</em></mark>
>
> <mark><em>That is the key shift we are demonstrating in this session.</em></mark>

---

# 5. Large Language Model vs Workflow vs Agent

## Main Notes

It is important to differentiate between a plain Large Language Model, a workflow, and an agent.

## Plain Large Language Model
A plain Large Language Model only generates responses.  
It does not perform external actions by itself.

## Workflow
A workflow follows fixed predefined steps.

For example:

1. fetch board details
2. fetch lists
3. create card

The path is already decided by the developer.

## Agent
An agent is more dynamic.

It decides which tool to use based on the user request and the current context. The path is not fully hardcoded step by step.

### Trello Example
If a user says, “Show me all cards in progress,” the agent may decide to:

1. identify the correct board
2. identify the list called In Progress
3. fetch cards from that list

If the user says, “Create a task and move it to Done,” the agent may choose a different sequence of tools.

**A workflow follows fixed steps, while an agent dynamically chooses the next step.**

## Speaker Notes

> <mark><em>This is a very important distinction because these terms are often mixed up.</em></mark>
>
> <mark><em>A plain <strong>Large Language Model</strong> only generates text.</em></mark>
>
> <mark><em>A <strong>workflow</strong> is different. A workflow has fixed steps already decided by the developer. It is useful, but the path is predefined.</em></mark>
>
> <mark><em>An <strong>agent</strong> is more dynamic. It looks at the user’s request and decides what sequence of actions makes sense.</em></mark>
>
> <mark><em>So if the user asks to see cards in progress, the agent may first find the right board, then identify the correct list, and then fetch the cards.</em></mark>
>
> <mark><em>If the request changes, the path may also change. That flexibility is what makes it agentic.</em></mark>

---

# 6. Why Agents Matter in Real Business Systems

## Main Notes

Agents are important because business users do not think in terms of APIs and functions. They think in terms of goals.

For example, business users say things like:

- create a task
- move this task to review
- show pending work
- update task description
- list all tasks in progress

They do not think in terms of:

- call endpoint
- pass list ID
- update card payload
- send API request

The real business value lies in integrating AI into software systems so that human intent can be translated into real application behavior through controlled tools.

This is the practical value of AI-driven software systems.

## Speaker Notes

> <mark><em>In real business environments, users do not think in technical implementation language. They do not say, ‘please call this API with this payload.’</em></mark>
>
> <mark><em>They speak in goals. They say things like create this task, move it to review, or show me pending work.</em></mark>
>
> <mark><em>The real business value lies in <strong>integrating AI into software systems</strong> so that this human intent can be translated into real software actions.</em></mark>
>
> <mark><em>That is why I am positioning this session not just as an agent demo, but as a simple example of an <strong>AI-driven software system</strong>.</em></mark>

---

# 7. Why LangChain Here

## Main Notes

For implementation, we need a framework that helps us connect a Large Language Model with tools in a structured way.

LangChain gives us a convenient way to:

- define tools
- connect tools with a model
- build an agent
- let the agent decide which tool to call

In today’s demo, I am not trying to build a very complex enterprise orchestration layer.

I am focusing on the core concept:

**How AI gets integrated into a software system and becomes capable of taking action through tools.**

That is exactly what we will demonstrate using Trello operations.

## Speaker Notes

> <mark><em>Now the next question is: why are we using <strong>LangChain</strong> here?</em></mark>
>
> <mark><em>The reason is simple. We need a structured way to define <strong>tools</strong>, connect them with a model, and allow the agent to choose among those tools.</em></mark>
>
> <mark><em><strong>LangChain</strong> gives us a practical way to do that for a teaching demo.</em></mark>
>
> <mark><em>I am intentionally keeping today’s scope focused. I am not trying to build a large production orchestration setup. I am trying to clearly show how <strong>AI gets integrated into a software system</strong> and becomes action-capable through tools.</em></mark>

---

# 8. Theory of the Trello Agent

## Main Notes

In the hands-on section, we will build a Trello Agent.

The user will interact in natural language.

The agent will interpret the intent and then use Trello-related tools such as:

- get board lists
- get cards from a list
- create a card
- move a card

So conceptually, our architecture is:

**User Prompt → Agent → Trello Tool → Trello API → Response → Final Answer**

This means:

- the user speaks in natural language
- the model understands what is needed
- the agent selects the correct Trello tool
- the tool calls Trello
- the result comes back to the user in a meaningful format

This is a practical example of how AI gets integrated into a widely used project management software and turns into a small AI-driven software system.

## Speaker Notes

> <mark><em>So now let me connect the theory to what we are actually building.</em></mark>
>
> <mark><em>In the hands-on section, we are going to create a <strong>Trello Agent</strong>. The user will simply type a <strong>natural language</strong> request. The model will interpret that request, choose the appropriate <strong>Trello tool</strong>, call the <strong>Trello API</strong> through that tool, and then return the result in a user-friendly way.</em></mark>
>
> <mark><em>So the architecture is straightforward: user prompt, agent, tool, <strong>Trello API</strong>, and then response back to the user.</em></mark>
>
> <mark><em>This is not just an isolated agent example. It is a small demonstration of how <strong>AI works with a real software platform</strong> and becomes part of an <strong>AI-driven software system</strong>.</em></mark>

---

# Closing Transition to Hands-On

## Main Notes

Now that the theory is clear, let us move to the practical part and see how AI gets integrated into a real software flow through LangChain, Trello tools, and a small working demo.

## Speaker Notes

> <mark><em>Now that the concepts are in place, let us move to the practical implementation and see how this works in code. We will take the model, connect it with <strong>Trello tools</strong> using <strong>LangChain</strong>, and observe how it becomes part of a small <strong>AI-driven software system</strong> rather than just a text generator.</em></mark>
