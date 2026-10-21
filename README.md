# Learning Chain Gang

A practical learning site for breaking AI frameworks into progressively deeper explanations without making the reader swallow the entire technical stack at once.

**Live site:** https://declan-goodwin.github.io/-Dgoodwin-Learning-Chain-Gang/

## What this project does

Learning Chain Gang organizes each topic into three levels of depth:

### Beginner — Explain it Simply
Focuses on the basic mental model:
- What is it?
- What problem does it solve?
- Who uses it?
- What does a practical use case look like?
- When might I actually need it?

### Intermediate — How the Components Work
Explains the major components, terminology, information flow, development workflow, related products, and tradeoffs.

### Advanced — Architecture and Implementation
Moves into system behavior:
- execution architecture
- state, memory, and persistence
- streaming and runtime behavior
- architectural choices
- implementation patterns
- failure modes and resilience
- debugging, observability, and evaluation
- deployment and production behavior
- when not to use the framework

The goal is not to replace official documentation. It is to build the mental model that makes the official documentation easier to use.

## Current topic

### [What is LangChain?](https://declan-goodwin.github.io/-Dgoodwin-Learning-Chain-Gang/whats-langchain)

The LangChain page currently includes Beginner, Intermediate, and Advanced sections covering the framework itself, LangGraph, LangSmith, agent architecture, tools, context, state, memory, middleware, structured output, persistence, evaluation, resilience, and production considerations.

## Design approach

The site uses a shared visual system built around:

- progressive disclosure through expandable learning levels
- readable content widths
- neon-blue heading hierarchy
- compact nested explanations
- decision-oriented definition lists
- callouts for principles and critical distinctions
- visual workflow treatments
- responsive layouts for smaller screens

The design intentionally becomes denser as the technical depth increases.

## Repository structure

- `index.md` — site landing page
- `whats-langchain.md` — current LangChain learning page
- `style.css` — shared site design system
- `_layouts/default.html` — basic Jekyll page shell
- `images/` — diagrams and supporting visuals

## Project status

This is an active learning project. Content and design are being refined as new framework topics are added.

Planned direction includes dedicated pages for adjacent parts of the ecosystem such as LangGraph and LangSmith, using the same Beginner → Intermediate → Advanced learning model.

## Why build it this way?

Technical documentation often assumes the reader already knows which concepts matter and how they relate.

Learning Chain Gang works in the opposite direction:

> Build the mental model first. Add technical depth only when the reader has somewhere to put it.

That makes the site as much an exercise in information architecture and technical communication as it is an AI-framework learning project.
