# Hexagonal Architecture Archetype

A Maven archetype designed to facilitate the implementation of the Hexagonal Architecture pattern (also known as Ports and Adapters) in your Java projects.

## Overview

This archetype provides a standardized, ready-to-use structure for developing applications with a clear separation between business logic and infrastructure concerns. It's designed to help teams maintain architectural consistency across projects and reduce initial setup time.

## Requirements

- Java 8 or above
- Maven 3.6.0 or above

## Installation

To install the archetype in your local Maven repository:

```bash
git clone [repository-url]
cd hexagonal-architecture-archetype
mvn install
```

## Usage

Generate a new project using the archetype:

```bash
mvn archetype:generate \
  -DarchetypeGroupId=es.omarall \
  -DarchetypeArtifactId=hexagonal-architecture-archetype \
  -DarchetypeVersion=0.1 \
  -DgroupId=[your-group-id] \
  -DartifactId=[your-artifact-id]
```

## Project Structure

The generated project follows the principles of hexagonal architecture with these main components:

### Hexagon Module
The core of your application containing:

- **Domain**: Business entities and domain logic
- **Ports**: Ports should be named according to what they are for, not according to any technology
  - Input Ports: Interfaces for application use cases
  - Repositories: Interfaces for fetching and storing data in external systems.
  - Recipients: Interfaces for sending data to external systems and forget about it.
- **Application**: Implementation of use cases and business rules

### Adapters Module
Actors interact with hexagon ports through adapters using a specific technology. 
An adapter is a software component that allows a technology to interact with a port of the hexagon.

Contains concrete implementations that connect your application to the outside world:

### SDK Module
Provides ready-to-use components to integrate your application with other systems:

- **a-spring-boot-starter**: A Spring Boot starter to facilitate integration with Spring Boot-based applications

## Benefits

- Enforced separation of concerns
- Highly testable code structure
- Business logic isolated from infrastructure details
- Flexibility to change technologies without affecting core business rules
- Scalable architecture suitable for both small applications and large enterprise systems

## Example

The archetype creates a basic project structure that you can extend with your specific domain model and adapters.