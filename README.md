# CLI Text Editor

A command-line text editor written in **C** that demonstrates the use of **Doubly Linked Lists**, **Stacks**, and **File Handling**. The editor allows users to create, edit, save, and load text documents while supporting **Undo** and **Redo** operations.

## Features

- Insert new lines of text
- Delete existing lines
- Undo previous operations
- Redo undone operations
- Save the document to a text file
- Load an existing document from a text file

## Data Structures Used

### Doubly Linked List
The document is stored as a **doubly linked list**, where each node represents a single line of text. This structure enables efficient insertion and deletion of lines without shifting the remaining content.

### Undo and Redo using Stacks
Two stacks are used to manage editing history:

- **Undo Stack**
  - Every insert or delete operation is recorded and pushed onto the undo stack.
  - Performing an undo removes the latest action from the undo stack, reverses the operation on the linked list, and pushes the action onto the redo stack.

- **Redo Stack**
  - Stores actions that have been undone.
  - Performing a redo pops the most recent action from the redo stack, reapplies it, and pushes it back onto the undo stack.

Whenever a new edit is made after an undo, the redo stack is cleared because the previous future history is no longer valid.

## File Handling

The editor supports persistent storage through text files.

- **Save:** Writes the current document to a text file.
- **Load:** Reads a previously saved text file and reconstructs the document as a doubly linked list.

This allows the document to be preserved across multiple program executions.

## Concepts Demonstrated

- Doubly Linked Lists
- Stack Data Structure
- Dynamic Memory Allocation
- File Handling in C
- Undo/Redo Implementation
- Command-Line Interface (CLI) Application
