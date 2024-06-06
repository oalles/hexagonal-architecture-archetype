# Hexagonal Architecture Archetype
This project provides a Maven archetype for generating the basic structure of a module that follows the hexagonal architecture.

## Requirements

- Java 8 or higher
- Maven 3.6.0 or higher

## Installation

To install the archetype in your local Maven repository, clone this repository and run the following command at the root of the project:

```bash
mvn install
```

## Project Structure

The generated project will include the following modules and directories:

- `hexagon`: This module contains your application's domain and the ports that define the operations that can be performed on it.
- `adapters`: This module contains the adapters that implement the ports defined in the `hexagon` module.

Each module has its own `pom.xml` file and follows the standard structure of a Maven project.