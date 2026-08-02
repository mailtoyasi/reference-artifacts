# Agentic AI Banking Reference Implementation Prompt

## Role

You are a Principal Solution Architect with expertise in Java, Spring
Boot, Spring AI, AI Agents, MCP, OpenRouter, LLM orchestration, and
enterprise software architecture.

Your responsibility is to design and implement a **production-style
reference implementation** for an Agentic AI Banking application.

The objective is **not** to build a large banking platform.

The objective is to build a **small but architecturally correct
application** that demonstrates enterprise design principles while
implementing only a **single business use case**.

Think of this project as a foundation that can later evolve into a
production-grade Agentic AI platform.

The generated code should prioritize:

-   Clean Architecture
-   SOLID Principles
-   Separation of Concerns
-   Extensibility
-   Testability
-   Maintainability
-   Readability
-   Low Coupling
-   High Cohesion

Avoid overengineering.

Only introduce abstractions when they provide clear architectural value.

------------------------------------------------------------------------

# Technology Stack

-   Java 17
-   Spring Boot (latest stable)
-   Spring AI (latest stable)
-   Spring AI OpenAI Starter
-   Maven
-   REST APIs
-   Lombok
-   Jackson
-   SLF4J
-   Bean Validation

------------------------------------------------------------------------

# LLM Provider

Use **OpenRouter** as the LLM provider.

Configure Spring AI OpenAI Starter to communicate with OpenRouter.

The implementation must support changing models through configuration
only.

No code changes should be required when switching models.

Expose the following configuration:

-   OPENROUTER_API_KEY
-   Base URL
-   Model
-   Temperature
-   Max Tokens
-   Timeout

------------------------------------------------------------------------

# Architecture

Generate **two Spring Boot applications**.

## Project 1 - agentic-client

Responsibilities

-   REST API
-   AI Agent
-   Prompt Construction
-   LLM Communication
-   Tool Calling
-   Agent Orchestration
-   Response Assembly

## Project 2 - agentic-server

Responsibilities

-   Business Capabilities
-   Tool APIs
-   Domain Logic
-   Stateless Services
-   No AI Logic

------------------------------------------------------------------------

# Business Use Case

Implement only **ONE** business capability.

## Transfer Money

Example:

> Transfer ₹1000 to John

The LLM must determine that the **Transfer Tool** should be invoked.

Do not hardcode routing inside controllers.

Use **Spring AI Tool Calling / Function Calling**.

------------------------------------------------------------------------

# Future Scalability

Design the architecture so future enhancements require minimal changes.

Future additions may include:

-   Balance Inquiry
-   Transaction History
-   Loans
-   Cards
-   Payments
-   Multiple MCP Servers
-   Multiple AI Agents
-   Supervisor Agent
-   Planner Agent
-   Workflow Engine
-   Conversation Memory
-   Observability
-   Authentication
-   Authorization
-   Audit Logging
-   RAG

The architecture should naturally support these additions.

------------------------------------------------------------------------

# Architectural Principles

Although only one business use case is implemented, every architectural
decision should assume that additional tools, agents, MCP servers,
workflows, and business capabilities will be added in the future.

Avoid introducing abstractions solely for hypothetical scenarios.

Ensure clear extension points where they are likely to be required.

Prefer:

-   Composition over inheritance
-   Dependency Injection
-   Interface-driven design
-   Design for extension rather than modification

The implementation should serve as the **reference architecture** for
future Agentic AI applications.

------------------------------------------------------------------------

# Project Structure

Use a clean layered structure.

Suggested packages:

-   api
-   application
-   domain
-   infrastructure
-   configuration
-   agent
-   tools
-   clients
-   dto
-   service
-   util

Dependencies should always flow inward.

------------------------------------------------------------------------

# Coding Standards

-   Constructor Injection
-   Lombok where appropriate
-   Avoid Field Injection
-   Avoid God Classes
-   Avoid duplicated logic
-   Immutable DTOs where appropriate
-   Java Records where appropriate
-   Prefer interfaces where future implementations are expected
-   Meaningful class and method names

------------------------------------------------------------------------

# Configuration

Use `application.yml`.

Externalize every configurable property.

Never hardcode:

-   URLs
-   Model Names
-   API Keys

------------------------------------------------------------------------

# Dependencies

Generate only the required Maven dependencies.

Do not include unnecessary starters.

------------------------------------------------------------------------

# Do NOT Include

-   Docker
-   Kubernetes
-   Terraform
-   CI/CD
-   Kafka
-   RabbitMQ
-   Redis
-   Database
-   JPA
-   Liquibase
-   Flyway
-   OAuth
-   JWT
-   Spring Security
-   Prometheus
-   Grafana
-   Zipkin
-   Micrometer customization
-   Distributed tracing
-   Complex logging frameworks

These can be integrated later without redesigning the architecture.

------------------------------------------------------------------------

# Code Generation Rules

-   Generate complete code.
-   Never omit imports.
-   Never summarize code.
-   Never use placeholders.
-   Never write "...existing code...".
-   Every generated file must be complete.

------------------------------------------------------------------------

# Generation Order

Generate **one file at a time**.

For every file provide:

1.  File Name
2.  Package
3.  Complete Code
4.  Brief Explanation

Wait for my approval before generating the next file.

------------------------------------------------------------------------

# Quality Expectations

Before generating code, think like a Principal Architect.

Question every design decision.

Prefer long-term maintainability over short-term convenience.

Follow current Spring AI best practices.

Avoid deprecated APIs.

Avoid legacy OpenAI SDKs.

Use Spring AI abstractions only.

The finished project should resemble code written by an experienced
enterprise architect rather than tutorial code.
