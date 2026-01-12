# Changelog

All notable changes to the **Starlight Programming Language** will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),  
and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [Unreleased]

### Added
- Initial language specification
- Lexer with detailed syntax error reporting
- Parser for expressions, statements, and blocks
- Evaluator with dynamic typing and runtime scope handling
- Built-in functions (`len`, `range`, `map`, `filter`, `reduce`, `keys`, `values`, etc.)
- Async / `await` support
- CLI execution support via `starlight` command
- Import system for local files and npm modules
- Clear runtime error messages with line and column indicators

### Changed
- Improved error formatting for syntax and runtime errors
- Enhanced variable resolution with name suggestions

### Fixed
- Division-by-zero runtime errors
- Unterminated string and comment detection
- Safer object and array indexing

---

## [0.1.0] – Initial Release

### Added
- Core language runtime
- Variables and expressions
- Control flow (`if`, `while`, `for`, `for-in`)
- Functions and arrow functions
- Arrays and objects
- CLI support

---

## Versioning

- **MAJOR**: Breaking language changes
- **MINOR**: New features, backwards compatible
- **PATCH**: Bug fixes and internal improvements
