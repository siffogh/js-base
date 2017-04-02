## About the JavaScript Engine (V8 Engine)
 In this section, I will only focus on the Google V8 engine for two reasons:
 - This section's intent is to explain the compiler process (which is extremely helpful when writing JavaScript code) rather than a history of the other engines.
 - Most modern JavaScript engines behave the same way when it comes to the knowledge covered in this section.

However, there are multiple other engines you can checkout (_SpiderMonkey_ by _Mozilla_ _Firefox_, _Nitro/JavaScriptCore_ by _Safari_, _Chakra_ by _IE_ ...)


### About the V8 engine
V8 is a **JavaScript engine**, written in C++. It has the following roles:
- **compiling** and **executing** JavaScript source code.
-  handling memory allocation for objects.
-  garbage collection of objects it no longer needs.

### Compilation Process
Compilation happens :v:mainly:v: in 3 steps:
- **Tokenizing/Lexing**: breaking up the code instructions into an array of meaningful words called tokens.
- **Parsing**: taking the array of tokens and translating it into a tree of the grammatical structure of the program called *AST* (Abstract Syntax Tree).
- **Code-Generation**: turning the AST into executable machine code.

#### When does compilation happen and what is the output?
- V8 and and other modern compilers are fast for because of two factors:
	- the compiler translates the code into machine code which can be executed directly.
	- they use **just-in-time (JIT)** compilation: compilation is done at during execution of program and not before it.


