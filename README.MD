Barky
Barky is inspired by Dane Hillard's Bark example of an application that demonstrates some basic software engineering principles such as:

Separation of concerns
Loose Coupling
Inheritance
Extensibility
Abstraction
Refactoring
This repository is an extension of Dane's example to also include testing.

Layered Architecture
At a basic level, the architecture is designed with a layered strategy to include the following common/typical elements:

Presentation Layer (will be a module called barky.py here)
Business Logic Layer (will be a module called commands.py here)
Presistence Layer (will be a module called database.py here)
Bare Bones Approach
Persistence
We will take a bare bones approach and connect directly to a sqlite database.

The DB Browser for SQLite tool will be useful to inspect the data and manage the database file.

The initial database wil consist of a table called bookmarks:

CREATE TABLE IF NOT EXISTS bookmarks
(
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    url TEXT NOT NULL,
    notes TEXT,
    date_added TEXT NOT NULL
);
Barky Refactored
Dane Hillard's code focused on a command-line interface, but we will refactor that code, in a new branch, to do the following:

Replace the custom data handling (the DatabaseManager module) with the SQLAlchemy O/RM
Replace the existing
Complete the implicit and explicit promises of the existing API
Replace the CLI as the exclusive interface in favor of a web-based REST API
Improve architecture:
SOLID
Repository Pattern and Unit of Work (understand how SQLAlchemy is really doing this)
Dependency injection