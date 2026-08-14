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
  
  <p>LangChain is an open-source framework that helps developers build applications powered by AI models like ChatGPT, Gemini, Claude, Copilot, and many more.
    <br><br>
  It provides ready-made components for connecting an AI model to tools, information, and instructions. Developers can combine these components instead of building every part of an AI application from scratch.</p>

 <h3>What Problem Does It Solve?</h3>
 <p> Building an AI application requires more than choosing an AI model. Developers also need ways to connect the model to other resources (like tools, information, or software) and coordinate how those resources will work together.
   <br><br>
   Creating all of those connections from scratch for every AI application would require a significant amount of time and effort. LangChain provides ready-made components and a common framework for connecting them. This gives developers a solid foundation that helps them to build useful applications faster.
   <br><br>
   For example, LangChain can help a developer connect an AI model to:
 </p>
  <ul>
    <li>A company's document library</li>
    <li>Databases</li>
    <li>Websites and search engines</li>
    <li>External applications</li>
    <li>Custom software tools</li>
  </ul>
  <p>Without these connections a model can generate responses, but it will not have the specialized knowledge or access to other systems that empower people at work and in their daily lives.</p>

 <h3>Who Uses It?</h3>
  <p>LangChain is mainly used by software developers and AI engineers. They use it to build applications such as:</p>
  <ul>
    <li>Customer-support assistants</li>
    <li>Research tools</li>
    <li>Document-search systems</li>
    <li>Video editors</li>
    <li>Scheduling assistants</li>
    <li> AI agents that can complete tasks</li>
  </ul>
<p>People do not usually interact with LangChain directly. Instead, they are the users of AI enabled applications that developers have built with it.</p>
</details>

<details>
 <summary style="cursor: pointer; display: list-item;">
    <h2 style="display: inline; margin-left: 5px;">LangChain Intermediate: How the Components Work</h2>
  </summary>
  
<p>LangChain is an open-source framework designed to simplify the creation of applications powered by Large Language Models (LLMs). <br>
  It provides a standardized way to connect these language models to:</p>
  <ul>
    <li>external data sources,</li>
    <li>application programming interfaces (APIs), and </li>
    <li>computation tools</li>
      </ul>
<p>Instead of managing complex AI prompts and connections from scratch, developers use its pre-built components to orchestrate multi-step workflows. This allows the AI to remember past parts of a conversation, execute sequential tasks, and dynamically choose the best tool to solve a user's request.</p>

</details>

<details>
   <summary style="cursor: pointer; display: list-item;">
    <h2 style="display: inline; margin-left: 5px;">LangChain Advanced: Architecture and Implementation</h2>
  </summary>
  
<p>LangChain is a composable orchestration framework that abstracts the complexities of integrating Large Language Models(LLMs) into software architectures through modular abstractions. 
 <br>
It formalizes state management and context window optimization via specialized Memory modules and manages data ingestion pipelines using Document Loaders and Text Splitters for Vector Retrieval-Augmented Generation (RAG).
<br>
By utilizing Chains and autonomous Agents equipped with ReAct (Reasoning and Acting) loops, it enables dynamic execution paths and tool call routing based on LLM outputs. 
<br>
Additionally, it streamlines prompt engineering through structured PromptTemplates and ensures predictable execution via the LangChain Expression Language (LCEL).</p>
</details>


 


