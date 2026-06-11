# tryp-logger

A professional logging library for the Trypillia programming language.

## Features

- **Object-Oriented API**: Create logger instances per module.
- **Log Levels**: Support for `DEBUG`, `INFO`, `WARN`, and `ERROR` levels with filtering.
- **JSON Formatting**: Built-in support for serializing logs to JSON for centralized log management (e.g. ELK, Datadog).
- **File Output**: Seamlessly write logs directly to a specified log file.

## Installation

You can install `tryp-logger` using the Trypillia Package Manager (`tryppm`):

```bash
tryppm install github:ChernegaSergiy/tryp-logger
```

## Usage

```javascript
load "tryp_modules/tryp-logger.try";

// Initialize loggers
let authLog = Logger("Auth");
let dbLog = Logger("Database");

// Configure file output and log level
dbLog.setFile("database.log");
dbLog.setLevel(LogLevel["WARN"]); // Only show WARN and ERROR

// Basic logging
authLog.info("User 'admin' logged in.");
authLog.debug("Token generated: 12345");

// JSON logging mode
let apiLog = Logger("API");
apiLog.enableJson(true);
apiLog.info("Request received: GET /users");

// Cleanup
dbLog.close();
```
