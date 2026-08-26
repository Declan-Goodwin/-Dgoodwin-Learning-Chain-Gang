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
    <br>
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
        <li>Adding human-in-the-loop review, approval, or decision points approval</li>
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
           <ul> 
             <li> Who experiences the problem?</li>
             <li> What are they try to accomplish?</li>
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

</details>


<details>
 <summary style="cursor: pointer; display: list-item;">
    <h2 style="display: inline; margin-left: 5px;">LangChain Advanced: Architecture and Implementation</h2>
  </summary>
      
  <p>
    LangChain is a composable orchestration framework that abstracts the complexities of integrating Large Language Models(LLMs) into software architectures through modular abstractions. 
    <br><br>
    It formalizes state management and context window optimization via specialized Memory modules and manages data ingestion pipelines using Document Loaders and Text Splitters for Vector Retrieval-Augmented Generation (RAG).
    <br><br>
    By utilizing Chains and autonomous Agents equipped with ReAct (Reasoning and Acting) loops, it enables dynamic execution paths and tool call routing based on LLM outputs. 
    <br><br>
  Additionally, it streamlines prompt engineering through structured PromptTemplates and ensures predictable execution via the LangChain Expression Language (LCEL).
  </p>
</details>





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




