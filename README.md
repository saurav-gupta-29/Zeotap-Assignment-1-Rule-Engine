# Overview
This application is a simple 3-tier rule engine designed to determine user eligibility based on various attributes like age, department, income, and spend. The system uses an Abstract Syntax Tree (AST) to represent and evaluate conditional rules. It supports dynamic rule creation, modification, and evaluation, and allows for the use of user-defined functions.

## Features
- *Rule Creation*: Define rules using a string format that is parsed into an AST.
- *Rule Combination*: Combine multiple rules into a single AST.
- *Rule Evaluation*: Evaluate the combined rule against user data to determine eligibility.
- *Rule Modification*: Modify existing rules by changing operators, operand values, or adding/removing sub-expressions.
- *User-Defined Functions*: Register and use custom functions in rules for advanced conditions.

## Design

### Data Structure
- *Node Class*: Represents a node in the AST.
  - type: Indicates the type of node ("operator" for AND/OR, "operand" for conditions).
  - left: Reference to the left child node (for operators).
  - right: Reference to the right child node (for operators).
  - value: Value for operand nodes (e.g., comparison values).

## APIs

1. *create_rule(rule_string)*:
   - Parses a rule string and constructs an AST.
   - Handles errors such as invalid formats or missing operators.

2. *combine_rules(rules)*:
   - Combines multiple rule strings into a single AST.
   - Uses "AND" by default to combine rules but can be customized.

3. *evaluate_rule(ast, data)*:
   - Evaluates the AST against a provided user data dictionary.
   - Supports logical operations and comparisons.

## Modifications and Extensions
- *Modify Existing Rules*: Change node types, values, or add/remove sub-expressions.
- *User-Defined Functions*: Register and use custom functions within rules for more complex conditions.

## External Dependencies

### Libraries
- *Python*: The application is written in Python and requires Python 3.x.
- *re Module*: Used for regular expressions to parse rule strings. This module is part of the Python Standard Library and does not require separate installation.
- *json Module*: Used for handling JSON data. This module is also part of the Python Standard Library.

### Database
This application integrates with MongoDB to store rules and metadata.

To set up MongoDB:
1. *Install MongoDB*: Download and install MongoDB from [here](https://www.mongodb.com/try/download/community). Follow the installation instructions for your operating system.
2. *Install pymongo*: The Python library to connect to MongoDB.
   ```bash
   pip install pymongo
