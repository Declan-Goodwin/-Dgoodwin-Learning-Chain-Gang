---
layout: default
---
<h1 style="display: flex; align-items: center; gap: 15px;">
  <img src="{{ '/images/LangChain-Logo-only.png' | relative_url }}" height="60" style="vertical-align: middle;" alt="LangChain Logo">
  <span>What is LangChain?</span>
</h1>


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
<!-- First Term: Model -->
<div class="term-container">
  <h4 class="term-title">Model:</h4>
  <span class="term-definition">The language model interprets inputs, generates responses, and can decide whether to call an available tool.</span>
  
  <div class="term-note">
    <strong class="term-note-label">Important Note:</strong> LangChain does not provide the model itself. Instead, it provides standardized interfaces for working with models from providers such as Anthropic, Google,                                                                and OpenAI.
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
    <li>Tool Results</li>
  </ul>
  <!-- This is more precise than saying the model receives “a prompt,” because an agent often works with an evolving sequence of messages. -->
</div>

  <div class="term-container">
  <h4 class="term-title">Tools:</h4>
  <span class="term-definition">Tools are functions that allow an agent to retrieve information or perform actions outside the model. Examples include searching the web, querying a database, retrieving an order, or                                     updating another application.</span>
   
  <div class="term-note">
    <strong class="term-note-label"> Important Note:</strong> A tool has a defined purpose, input structure, and output. The model can request a tool call, but the surrounding application executes it.
  </div>
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




