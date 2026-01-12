# Starlight Programming Language – Roadmap

This roadmap outlines the planned direction and evolution of the **Starlight Programming Language**.
It is a living document and may change based on community feedback and real-world usage.

---

## Phase 1 — Foundation (Completed / In Progress)

### Language Core
- Lexer with detailed syntax error reporting
- Parser for expressions, statements, and blocks
- Evaluator with scoped environments
- Dynamic typing
- Clear runtime error messages with source context

### Core Features
- Variables (`let`, `define`)
- Control flow (`if`, `else`, `while`, `for`, `for-in`)
- Functions and arrow functions
- Arrays and objects
- Built-in functions (`len`, `range`, `map`, `filter`, `reduce`, etc.)
- Import system (local files and npm modules)
- Async / `await` support
- CLI execution (`starlight file.sl`)

---

## Phase 2 — Language Stability

### Syntax & Semantics
- Finalize operator precedence rules
- Improve logical and nullish handling
- Optional language features review (keep core minimal)
- Stricter error diagnostics and hints

### Standard Library
- File system utilities
- Date and time utilities
- Math helpers
- String utilities
- JSON helpers

### Tooling
- REPL mode
- Better CLI help (`starlight --help`)
- Exit codes for runtime and syntax errors

---

## Phase 3 — Developer Experience

### Documentation
- Full language reference
- Standard library documentation
- Cookbook / examples
- Error message reference

### Ecosystem
- Official npm helper packages
- Community module guidelines
- Package naming conventions

### Debugging
- Stack traces for function calls
- Optional debug mode
- Execution step tracing

---

## Phase 4 — Performance & Reliability

- AST optimization passes
- Faster evaluator execution
- Reduced memory usage
- Better async handling
- Improved import caching

---

## Phase 5 — Community & Growth

- Contribution guidelines
- Issue templates
- Language proposals process
- Community examples repository

---

## Long-Term Ideas

- Optional static analysis tools
- Language server (LSP) support
- Editor syntax highlighting
- Formatter / linter
- Web and embedded runtimes

---

## Guiding Principles

- Simple syntax
- Clear error messages
- Small, powerful core
- Script-first, developer-friendly

---

**Status:** Early development  
**Feedback & Contributions:** Welcome
