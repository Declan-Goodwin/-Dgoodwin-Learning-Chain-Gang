---
layout: default
---
<header class="page-heading"> 
<h1 style="display: flex; align-items: center; gap: 15px;">
  <img src="{{ '/images/LangChain-Logo-only.png' | relative_url }}" height="60" style="vertical-align: middle;" alt="LangChain Logo">
  <span>What is LangChain?</span>
</h1>
  <p class="page-tagline">
    Explore LangChain at three levels of technical depth. Start with the beginner explanation, then expand the intermediate and advanced sections as you become more familiar.
  </p>
</header>

<details>
  <summary style="cursor: pointer; display: list-item;">
    <h2 style="display: inline; margin-left: 5px;">LangChain Beginner: Explain it Simply</h2>
  </summary>
  
  <p>LangChain is an open-source framework that helps developers build applications powered by AI models. 
    <br><br>
  It provides reusable components for connecting AI models to data, tools, and other software. It also helps developers coordinate how those components work together. Developers can combine these components instead of building every part of an AI application from scratch.</p>

 <h3>What Problem Does It Solve?</h3>
 <p>Building an AI application requires more than choosing an AI model. Developers also need ways to connect the model to outside resources like tools, information, and software, and coordinate how those resources work together.
     <br><br>
   Building all of those connections from scratch can require a significant time and effort. LangChain provides reusable components and a common framework for connecting them. This gives developers a consistent starting point for building useful applications faster.
     <br><br>
   For example, LangChain can help a developer connect an AI model to:
 </p>
  <ul>
    <li>A company's document library</li>
    <li>Databases</li>
    <li>Web search and other external data sources</li>
    <li>External applications and Application Programming Interfaces (APIs)</li>
    <li>Custom software tools</li>
  </ul>
  <p> Without connections like these, a model can generate responses but cannot retrieve specialized information or interact with external systems.</p>

 <h3>Who Uses It?</h3>
  <p>LangChain is mainly used by software developers and AI engineers. They use it to build applications such as:</p>
  <ul>
    <li>Customer-support assistants</li>
    <li>Research tools</li>
    <li>Document-search systems</li>
    <li>Scheduling assistants</li>
    <li> AI agents that can complete tasks</li>
  </ul>
<p>Most people do not interact with LangChain directly. Instead, they use the AI-enabled applications that developers have built with it.</p>

<h3>Practical Use Case </h3>
<p>Imagine a company wants an AI assistant that can answer questions about customer orders. 
   <br><br>
By itself, the AI model will understand a customer's question, but it does not automatically have access to the company’s order information. Without that connection, it cannot determine what a customer ordered, how much it cost, or whether it has shipped.
  <br><br>
A developer could use LangChain as part of an application that connects the model to the company’s order system.
  <br><br>
When a customer asks, "Where is my order?", the application can:
  <ol>
  <li> Identify the customer and order.</li>
  <li> Retrieve the order's current status.</li>
  <li> Provide the relevant information to the AI model.</li>
  <li> Generate a clear response for the customer.</li>
</ol>
LangChain helps the developer connect and coordinate the components involved in this process.
</p>

<h3>When Might I Need It?</h3>
   <p>You might use LangChain when an AI application needs to do more than generate a response using the model’s training data.
   <br>
   For example, an application might need to:
   <ul>
     <li> Retrieve information from an outside source</li>
     <li> Search a collection of documents</li>
     <li> Use software tools or APIs</li>
     <li> Maintain information during a conversation</li>
     <li> Decide which action to take next</li>
     <li> Complete a task involving several steps</li>
   </ul>
   If your application only needs to send one prompt to an AI model and return its response, you may not need LangChain.
   </p>
</details>

<details>
 <summary style="cursor: pointer; display: list-item;">
    <h2 style="display: inline; margin-left: 5px;">LangChain Intermediate: How the Components Work</h2>
  </summary>
      <h3> Major Components & Terminology</h3>

<div class="term-container">
  <h4 class="term-title">Model:</h4>
  <span class="term-definition">The language model interprets inputs, generates responses, and can decide whether to call an available tool.</span>
  <div class="term-note">
   <span> <strong class="term-note-label">Important Note:</strong> LangChain does not provide the model itself. Instead, it provides standardized interfaces for working with models from providers such as Anthropic, Google,                                    and OpenAI.</span>
  </div>
</div>

<div class="term-container">
  <h4 class="term-title">Messages:</h4>
  <span class="term-definition">Messages are the structured inputs and outputs exchanged with a chat model. They can represent:</span>

  <ul style="line-height: 1.5; margin-top: 8px;">
    <li>Developer or system instructions</li>
    <li>User input</li>
    <li>Model responses</li>
    <li>Tool requests</li>
    <li>Tool results</li>
  </ul>
  <!-- This is more precise than saying the model receives “a prompt,” because an agent often works with an evolving sequence of messages. -->
</div>

  <div class="term-container">
  <h4 class="term-title">Tools:</h4>
  <span class="term-definition">Tools are functions that allow an agent to retrieve information or perform actions outside the model. Examples include searching the web, querying a database, retrieving an order, or updating another application.</span>
   
  <div class="term-note">
    <strong class="term-note-label"> Important Note:</strong> A tool has a defined purpose, input structure, and output. The model can request a tool call, but the surrounding application executes it.
  </div>
</div>

<div class="term-container">
  <h4 class="term-title">Agent:</h4>
  <span class="term-definition">An agent combines a model with instructions, tools, and behavior that governs how they work together. LangChain currently defines the basic agent pattern as a model calling tools in a loop until it can complete the task.
  </span>

<div class="term-note">
  <strong class="term-note-label"> Agent = Model + Harness</strong> 
</div>
<br>
  <span class="term-definition"> The harness is the operational environment and control architecture that wraps around a core language model. It consists of instructions, tools, middleware and other components that enable the agent to execute tasks.      </span>
 </div>

 <div class="term-container">
  <h4 class="term-title">Context:</h4>
  <span class="term-definition">The information provided to a model when it is asked to generate a response or make a decision. Context can include instructions, messages, tool descriptions, tool results, and information retrieved from other sources.
  </span>

<div class="term-note">
  <span> <strong class="term-note-label"> Important Note: </strong> The model can only reason from information included in its current context or learned during training. Information stored elsewhere must be retrieved and added to the context before the model can use it.</span>
</div>
</div>

<div class="term-container">
  <h4 class="term-title">Context Window:</h4>
  <span class="term-definition">The maximum amount of information a model can process during a single call. Its size is measured in tokens and includes the input provided to the model and the space used for the generated output. Because the context window is limited, an application may need to select, summarize, or remove information before calling the model.</span>
</div>

<div class="term-container">
  <h4 class="term-title">State:</h4>
  <span class="term-definition">The evolving information an application maintains while an agent or workflow is running. State commonly includes conversation messages, tool results, uploaded files, authentication status, and other values needed to continue the task.
  <br>
  When the application calls the model, it may use some portion of that state to construct the model’s current context. </span>
<div class="term-note">
  <span> <strong class="term-note-label"> Important Note: </strong> State belongs to the application’s execution process. It is not identical to the context presented to the model. </span>
</div>
</div>

  <div class="term-container">
  <h4 class="term-title">Memory:</h4>
  <span class="term-definition">The mechanisms an application uses to preserve and retrieve information beyond a single model call. It is comprised of <em>short-term memory</em> and <em>long-term memory</em>.
    <br>
    Memory <strong>does not mean</strong> that the model permanently remembers information itself. Instead, the application stores information and makes it available when it becomes relevant to the execution process.
  </span>
  </div>
    <div class="subdefinition">
      <span><strong class="subterm">Short-Term Memory:</strong> Information preserved within a single conversation or thread. In a LangChain agent, short-term memory is managed as part of the agent’s state and can be persisted so the thread can resume later.
     <p>Examples include:</p>
  <ul style="line-height: 1.5; margin-top: 8px;">
    <li>Conversation history</li>
    <li>Results from earlier tool calls</li>
    <li>Files associated with the current thread</li>
    <li>Progress made during a multi-step task</li>
  </ul>
        Long conversations may need to be trimmed or summarized because the entire history may not fit, or may not remain useful within the model’s context window.
      </span>
    </div>
  <div class="subdefinition">
      <span><strong class="subterm">Long-Term Memory:</strong> Information stored across different conversations or threads. It allows an application to retain information such as user preferences, historical details, or previously extracted insights and retrieve them when relevant.</span>  
    <div class="term-note">
    <span> <strong class="term-note-label"> Important Note: </strong> Long-term memory is not automatically included in every model call. The application must retrieve relevant information and add it to the model’s current context. </span>
    </div>
     <p><strong>Quick Analogy:</strong> Long-term memory is remembering all the summer trips you and your best friend have taken together. Short-term memory is remembering the destinations your friend has suggested while you plan this summer’s trip.</p>
  </div>
    
<div class="term-container">
  <h4 class="term-title">Middleware:</h4>
  <span class="term-definition">Middleware lets developers inspect or modify what happens at different points in the agent loop.</span>
   <p style="line-height: 1.5; margin-top: 8px;"> Developers can use middleware to add functionality such as: </p> 
     <ul style="line-height: 1.5; margin-top: 8px;">
        <li>Logging agent activity</li>
        <li>Applying guardrails</li>
        <li>Adding human-in-the-loop review, approval, or decision points</li>
        <li>Retries and fallbacks</li>
        <li>Modifying model instructions</li>
        <li>Restricting access to tools</li>
        <li>Summarizing conversation history</li>
      </ul>
    <p>Rather than completing an agent’s primary task, middleware adds behavior around how the task is completed. This behavior can guide, constrain, or support the process.</p>
  </div>

<div class="term-container">
   <div class="term-definition">
    <h4 class="term-title">Structured Output:</h4>
      <span>Is a way of requiring a model’s response to follow a predefined structure, rather than returning only free-form text.</span>
       <p>Developers use structured output when another part of the application needs to reliably identify and use specific pieces of information from the response. </p>
       <p class="definition-example"> <strong>For example:</strong> Instead of responding with a paragraph about an order, the model could return separate fields for the order number, shipping status, and estimated delivery date. </p>
       <p class="term-comparison"> <strong>Middleware</strong> influences how an agent completes a task. <strong>Structured output</strong> defines how the final result must be organized. </p>
  </div> 
</div>

 <h3> How Information Moves Through It </h3>
   <p> A simplified process execution would look like: </p>
    <ol style="line-height: 1.5; margin-top: 8px;">
          <li> The user submits a request.</li>
          <li> The application adds the request to the agent’s state.</li>
          <li> LangChain prepares the model’s context using instructions, conversation history, available tools, and relevant state.</li>
          <li> The model determines whether it can answer directly or needs a tool.</li>
          <li> <em>If needed</em>, the model requests a tool call using structured inputs.</li>
          <li> The application executes the tool and returns its result to the agent.</li>
          <li> The result becomes additional context for the model.</li>
          <li> The model may call another tool or generate a final response.</li>
          <li> The application returns the response to the user.</li>
        </ol>
  <div>
   <span> <strong class="term-note-label"> Critical Insight: </strong> Information does not simply travel from the user to the model and back. It may circulate through the agent loop several times as the model requests tools and receives their results.     </span>
  </div>
  <br>
<img src="{{ '/images/Agent-Workflow-Update.png' | relative_url }}" width="550" height="550" style="display: block; margin: 0 auto;" alt="Agent Process Flow">

 <h3> Typical Development Workflow </h3>
   <ol class="development-workflow"> 
     <li>
       <h4>Frame the Problem</h4>
         <p>Before selecting a model or creating an agent, define the problem the application is intended to solve. This helps prevent teams from building an AI application simply because the technology is available. </p>
         <p>Consider:</p>
           <ul style="line-height: 1.5; margin-top: 8px;">
             <li> Who experiences the problem?</li>
             <li> What are they trying to accomplish?</li>
             <li> Where does the current process create difficulty, delay, or risk?</li>
             <li> What evidence confirms that the problem exists?</li>
             <li> What measurable outcome would represent an improvement?</li>
             <li> Does the problem require an AI agent, or could a simpler solution work better?</li>
           </ul>
      </li>
      <li> 
        <h4>Define the Application's Requirements</h4>
          <p>Determine what the application must do to address the validated problem. Identify the information it needs, the actions it must perform, the people and systems it will interact with, and any operational or security constraints.</p>
      </li>
      <li> 
        <h4>Select the Model</h4>
          <p>Choose a model based on the capabilities the application requires, along with factors such as cost, response time, context-window size, privacy requirements, and provider availability.</p>
      </li>
      <li>
        <h4>Define Instructions and Tools</h4>
          <p>Write the agent’s instructions and define the tools it may use. Each tool should address a specific application requirement and have clearly defined inputs and outputs.</p>
      </li>
      <li>
        <h4>Configure the Agent</h4>
          <p>Connect the model, instructions, and tools. Add state, memory, middleware, and structured output where the application’s requirements justify them.</p>
      </li>
      <li>
        <h4>Test and Evaluate</h4>
          <p>Test the application using representative scenarios, including expected inputs, ambiguous requests, tool failures, and potentially unsafe actions.</p>
          <p>Evaluate both technical performance and whether the application improves the original user problem.</p>
      </li>
      <li>
        <h4>Deploy and Monitor</h4>
          <p>Deploy the application into its intended environment. Monitor behavior, cost, response time, tool usage, failures, and user outcomes.</p>
      </li>
      <li> 
        <h4>Improve the Application</h4>
          <p>Use evaluation results, execution traces, and user feedback to revise the application. Improvements may involve changing instructions, tools, models, control logic, or even reconsidering whether the original solution was appropriate.</p>
      </li>
   </ol>
      <strong class="term-note-label"> Frame the problem -> build the application -> measure the outcome -> reconsider the solution. </strong>
<!-- Code example? --> 

 <h3> How it Interacts with Other LangChain Products </h3>  
   <div class="term-container">
      <h4 class="term-title">LangGraph: Controlling Agent Workflows</h4>
        <span class="term-definition">LangGraph is a lower-level orchestration runtime for building and executing stateful agents and workflows.</span>
          <p>LangChain agents are built on LangGraph. LangChain provides higher-level components for configuring common agent behavior, while LangGraph provides the underlying capabilities for maintaining state and controlling how execution progresses.            </p>
          <p>Developers may work directly with LangGraph when they need greater control over execution paths, persistence, human decision points, or workflows combining predetermined steps with model-driven decisions. 
          </p>
    <div class="term-note">
      <span> <strong class="term-note-label">When to Use</strong> Use LangChain when its higher-level agent architecture provides enough control. Work directly with LangGraph when the application requires a more explicitly designed workflow. </span>
    </div>
   </div>
  <div class="term-container">
      <h4 class="term-title">LangSmith: Observing and Evaluating Applications</h4>
        <p>LangSmith is a platform for observing, evaluating, and improving AI applications.</p>
        <p>It records application activity as traces, allowing developers to inspect model calls, tool usage, workflow steps, errors, and final outputs. Developers can also test applications against datasets, compare versions, and monitor behavior in               production.
        </p>
        <p>LangSmith works with LangChain and LangGraph, but it is not required to run applications built with either product. It can also be used with other AI frameworks.</p>
     <div class="term-note">
      <span> <strong class="term-note-label">The Through Line:</strong> <strong>LangChain</strong> helps build the application. <strong>LangGraph</strong> controls more customized execution. <strong>LangSmith</strong> helps developers understand and improve how the application behaves. </span>
    </div>
  </div>
 <h3>Benefits and Tradeoffs</h3>
  <p><strong>Benefits:</strong></p> 
    <ul style="line-height: 1.5; margin-top: 8px;">
      <li>Provides standardized interfaces across model and tool providers</li>
      <li>Reduces the amount of application plumbing developers build themselves</li>
      <li>Offers reusable agent patterns and integrations</li>
      <li>Supports memory, middleware, structured output, and tool calling</li>
      <li>Makes it easier to replace or reconfigure individual components</li>
      <li>Integrates with LangGraph for greater workflow control</li>
      <li>Integrates with LangSmith for tracing and evaluation</li>
    </ul>
  <p><strong>Tradeoffs:</strong></p> 
     <ul style="line-height: 1.5; margin-top: 8px;">
       <li>Adds another abstraction layer that developers must understand</li>
       <li>Can be unnecessary for simple model requests</li>
       <li>Agent behavior can be nondeterministic and difficult to test</li>
       <li>Additional tools and agent steps increase latency and cost</li>
       <li>Framework updates can require developers to revise existing applications</li>
       <li>Prebuilt abstractions may provide less control than custom code</li>
       <li>Connecting a tool does not automatically make its data accurate, safe, or appropriate</li>
       <li>Developers remain responsible for access controls, error handling, validation, and monitoring</li>
     </ul>
  </details>


<details>
 <summary style="cursor: pointer; display: list-item;">
    <h2 style="display: inline; margin-left: 5px;">LangChain Advanced: Architecture and Implementation</h2>
  </summary>
<p> At the beginner level, LangChain can be understood as a framework for connecting models to information, tools, and instructions. At the intermediate level, those components become a workflow. At the advanced level, the important questions change:</p>
  <ul>
    <li>How is that workflow executed?</li>
    <li>What state survives between steps?</li>
    <li>What happens when something fails?</li>
    <li>How can execution be inspected, resumed, evaluated, and deployed reliably?</li>
  </ul>   
<p>Advanced LangChain development is therefore less about adding more components and more about controlling the behavior of the system those components create.</p>
  
<h3>Architecture and Execution Model</h3>
  <p>At Intermediate we talked about components interacting. Here we explain that those interactions ultimately create an <strong>execution topology</strong>.</p>
  <p>A modern LangChain agent is not simply:</p>
    <div class="term-note">
      <span> <strong class="term-note-label"> User -> Prompt -> Model -> Answer </strong> </span>
    </div>
  <p>It is closer to:</p>
   <div class="term-note">
      <span> <strong class="term-note-label"> Input -> State -> Model -> Decision -> Tool -> State Update -> Model -> ... -> Output </strong> </span>
  </div>
  <p> When create_agent is used, LangChain constructs that agent on a LangGraph-based runtime. The graph contains steps such as model calls and tool execution, connections controlling how execution moves between them, and middleware that can intervene at different points in that process. The loop continues until the model produces a final response or another stop condition is reached.
  </p>
  <p><strong>LangChain</strong> provides higher-level abstractions for assembling AI applications. <strong>LangGraph</strong> provides the lower-level orchestration model used when those applications require explicit control over execution, state, persistence, branching, or recovery.
  </p>
  <p> A LangChain agent may therefore <em>run on LangGraph</em> without the developer manually constructing a graph. When an application's execution logic becomes more specialized, that same developer can move downward and work directly with LangGraph.    </p>
  <div class="term-container">
    <h4 class="term-title">Workflow vs. Agent</h4>
       <div class="term-note">
         <span> A <strong class="term-note-label">Workflow </strong> has substantially predetermined execution paths. </span>
       </div>
       <div class="term-note">
         <span> An <strong class="term-note-label">Agent</strong> can dynamically choose its next action based on the model, available tools, and current state.</span>
       </div>
  </div>
    <p>LangGraph supports both patterns, and they can be combined. A deterministic workflow might classify a request first, route it to a specialized agent, require human approval before a sensitive action, and then return to deterministic processing afterward.
    </p>
    <p>Insert Diagram Here :)</p>
<h3>State, Persistence, and Memory</h3>
           




 <!-- 
   <p>
    LangChain is a composable orchestration framework that abstracts the complexities of integrating Large Language Models(LLMs) into software architectures through modular abstractions. 
    <br><br>
    It formalizes state management and context window optimization via specialized Memory modules and manages data ingestion pipelines using Document Loaders and Text Splitters for Vector Retrieval-Augmented Generation (RAG).
    <br><br>
    By utilizing Chains and autonomous Agents equipped with ReAct (Reasoning and Acting) loops, it enables dynamic execution paths and tool call routing based on LLM outputs. 
    <br><br>
  Additionally, it streamlines prompt engineering through structured PromptTemplates and ensures predictable execution via the LangChain Expression Language (LCEL).
  </p>
--> 
<!-- What to preserve for later -->

<!-- Keep the deeper material in your working notes. It is not wasted; it belongs elsewhere: -->

<!--
Detailed LangGraph customer-order workflow → dedicated LangGraph page
Traces and diagnostic example → dedicated LangSmith page
Offline versus online evaluation → LangSmith intermediate page
Deployment modes → LangSmith advanced page
Full three-product architecture table → ecosystem overview or homepage 
-->
<!--
<div class="term-container">
    <h4 class="term-title">LangGraph: The Runtime Beneath LangChain Agents</h4>
    <span class="term-definition">LangGraph is a lower-level orchestration runtime for building and executing stateful agents and workflows.</span>
      <p>In this context, <strong>orchestration</strong> means controlling how an application progresses through different steps, what information it maintains, and what happens when the application must branch, pause, resume, or wait for human input.         </p>
      <p>LangGraph provides execution capabilities such as:</p>
        <ul style="line-height: 1.5; margin-top: 8px;">
          <li>Maintaining and persisting state</li>
          <li>Controlling how a workflow moves between steps</li>
          <li>Combining predetermined steps with model-driven decisions</li>
          <li>Pausing execution for human review or approval</li>
          <li>Resuming interrupted or long-running tasks</li>
          <li>Streaming updates while an application runs</li>
        </ul>
  </div>
     <div class="subdefinition">
       <strong class="subterm">How LangChain and LangGraph Work Together</strong>
         <p>LangChain agents are built on LangGraph. When a developer creates an agent through LangChain, LangChain provides the higher-level components and interfaces used to configure the agent. LangGraph provides the underlying runtime that executes the agent loop and maintains its progress.</p>
           <ul style="line-height: 1.5; margin-top: 8px;">
             <li><strong>LangChain</strong></li>
               <p>Provides higher-level abstractions for assembling models, tools, instructions, middleware, and common agent behavior</p>
             <li><strong>LangGraph</strong></li>
               <p>Provides the runtime for executing and controlling stateful agents and workflows</p>
           </ul>
         <p>A developer using LangChain may benefit from LangGraph without interacting with it directly. LangGraph’s execution capabilities operate beneath the higher-level LangChain agent interface.</p>
         <p>The products are therefore complementary layers rather than competing ways to build the same application.</p>
     </div>
     <div class="subdefinition">
           <strong class="subterm">When Would a Developer Use LangGraph Directly?</strong>
           <p>LangChain is often sufficient when an application follows a common agent pattern: the model receives a request, selects and calls tools as needed, and continues until it can produce a response.</p>
           <p>A developer might work directly with LangGraph when the application requires more explicit control over how that process unfolds.</p>
           <p>For example, direct LangGraph development may be useful when an application must:</p>
             <ul style="line-height: 1.5; margin-top: 8px;">
               <li>Follow some steps in a predetermined order</li>
               <li>Choose between different execution paths</li>
               <li>Maintain custom information throughout a workflow </li>
               <li>Pause at defined decision points for human involvement</li>
               <li>Resume a task after an interruption</li>
               <li>Coordinate a long-running or multi-stage process</li>
               <li>Combine predictable software logic with model-driven decisions</li>
             </ul>
         <p>Using LangGraph directly does not require abandoning LangChain. Developers can still use LangChain’s model interfaces, tools, and other components within a LangGraph workflow.</p>
     </div>
     <div class="subdefinition">
          <strong class="subterm">Practical Example</strong>
            <p>Consider an AI customer-service application that handles order problems. A basic LangChain agent might:</p>
             <ol style="line-height: 1.5; margin-top: 8px;">
               <li>Interpret the customer’s question.</li>
               <li>Use a tool to retrieve the order.</li>
               <li>Review the order status.</li>
               <li>Generate an answer for the customer.</li>
             </ol>
           <p>That common model-and-tool loop may be sufficient when the application only needs to locate information and explain it.</p>
           <p>The workflow becomes more complex if the application must also:</p>
             <ol style="line-height: 1.5; margin-top: 8px;">
               <li>Verify the customer’s identity.</li>
               <li>Retrieve the order and shipping history.</li>
               <li>Determine whether the package is delayed, lost, or delivered.</li>
               <li>Follow a different process for each condition.</li>
               <li>Request human approval before issuing a refund above a defined amount.</li>
               <li>Open a claim with the shipping provider.</li>
               <li>Preserve its progress while waiting for the claim result.</li>
               <li>Resume the process when new information becomes available.</li>
             </ol>
           <p>LangGraph allows the developer to represent these steps, decision points, and interruptions as an explicitly controlled workflow. Model-driven decisions can still be used where flexibility is helpful, while predetermined logic governs steps that must follow established rules.</p>
     </div>
     <div class="subdefinition">
          <strong class="subterm">Which One Should You Use?</strong>
            <p>Use <strong>LangChain</strong> when its higher-level agent architecture provides enough control for the application.</p>
            <p>Use <strong>LangGraph</strong> directly when the application requires customized execution paths, persistent state, human decision points, or a deliberate combination of predictable and model-driven behavior.</p>
            <p>The decision is not necessarily <strong>LangChain</strong> or <strong>LangGraph.</strong> It is often a decision about which layer of control the developer needs to work with.</p>
     </div>
  <div class="term-container">
    <h4 class="term-title">LangGraph: The Runtime Beneath LangChain Agents</h4>
</details>
-->




<!-- Me thinking I'm cooler than I am, trying to see if I can add wiki like features - like overing over a word to display a micro menu that displays the definition -->
<!-- The house has a problem with its <span class="wiki-hover">Mechanical<span class="micro-menu"><strong> Systems;</strong><br>this includes HVAC, ductwork, and ventilation.<br><a href="/wiki/mechanical">Read Wiki Page →</a></span></span> systems. 
-->

<!-- 
<style>
.wiki-hover { position: relative; border-bottom: 1px dashed #0066cc; cursor: help; color: #0066cc; dplay: inline-block; }
.wiki-hover .micro-menu { visibility: hidden; width: 220px; background-color: #ffffff; color: #333333; text-align: left; border: 1px solid #cccccc; border-radius: 4px; padding: 10px; position: absolute; z-index: 1; bottom: 125%; left: 50%; margin-left: -110px; box-shadow: 0px 4px 8px rgba(0,0,0,0.1); }
.wiki-hover:hover .micro-menu { visibility: visible; }
</style>
-->




