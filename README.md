# DeepgramVoiceAgent


DeepgramVoiceAgent

Overview

DeepgramVoiceAgent is a voice interaction application built using Node.js. It has a modular design and supports two types of storage systems. One is in-memory storage for quick testing and development, and the other is database storage that uses SQL database accessed through drizzle-orm.

The application manages users, conversations, and messages to allow real-time voice or text conversations.

Environment and System Modules

Node.js version 20.18.1

Supports package managers like npm, yarn, pnpm, or bun

Uses Prettier version 3.3.3 for code formatting

Uses TypeScript Language Server version 4.3.3

Supports CSS and HTML Language Servers

Core Modules

The application works with three main data models:

User: represents users of the app

Conversation: represents chat conversations linked to users

Message: represents individual messages inside conversations

Storage Interface

The storage interface defines methods to perform create, read, update, and delete operations on these models. The main methods are:

getUser: get a user by their ID

getUserByUsername: get a user by username

createUser: add a new user

createConversation: add a new conversation

getConversation: get a conversation by its ID

getUserConversations: get all conversations for a specific user

createMessage: add a new message to a conversation

getConversationMessages: get all messages in a conversation

getLatestConversation: get the most recent conversation, optionally for a user

Storage Implementations

There are two implementations of the storage interface:

In-memory Storage

This stores data in memory using JavaScript maps. It auto-increments IDs and is useful for development or testing but does not save data permanently.

Database Storage

This uses the drizzle-orm library to interact with a relational database. It performs SQL queries to save and retrieve data. This storage persists data and is suitable for production.

How to Use

Setup

Make sure Node.js version 20.18.1 is installed. Install project dependencies using your preferred package manager like npm install. Configure your database connection in the db module.

Usage

Import the storage instance from the storage file. Use the async methods to create and fetch users, conversations, and messages.

For example, create a user, create a conversation for that user, add messages, and fetch all messages from the conversation.

Project Structure

The main files include:

storage.ts: defines the storage interface and its implementations

db.ts: handles database configuration and setup

shared schema files: define database tables and types for users, conversations, and messages

Notes

In-memory storage loses data when the app restarts. For real applications use the database storage with a persistent database. Date and time fields like createdAt and timestamp are handled automatically either in memory or by the database.

License

This project uses the MIT License.

