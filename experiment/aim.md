A High Level Programming Language like C provides **abstractions** to program an underlying computing system. The following is a broad classification of various abstractions.

1. **Data Abstractions:** Data Abstractions provide certain primitive data types like int, float, char etc. and a mechanism (like structures, arrays etc.) to hierarchilaly compose the primitive data types to create new abstract data types.

2. **Data Processing Abstractions:** Data Processing Abstractions provide operations (like addition, multiplication, comparison etc.) which act on the primitive data types which can again be composed to act on user-defined data types.

3. **Control Abstractions:** Control abstractions include language features like conditional/unconditional goto, if-then-else, for-loop, while-loop etc. A language which doesn't support at least one these Control Abstractions will not be Turing Complete which means there exists certain functions which are not computable using the language features alone.

4. **Procedural Abstraction:** Procedures allows a user to define his/her own operation to act upon primitive or user defined data types. Further it allows modular development of programs enabling software readability, maintainability and efficiency also.

5. **More Abstractions:** Object-oriented languages like C++ and Java provide features like classes, inheritance, polymorphism etc. Similary different langugages can provide different sets of abstraction depending upon their design philosophy and utility.

In this assignment and in the next few we shall learn how to implement these High Level Language Abstractions in the Assembly Language. There are 2 sets of assignments corresponding to MIPS and ARM Instruction Set Architectures (ISAs). Both MIPS and ARM ISA follow RISC philosophy.