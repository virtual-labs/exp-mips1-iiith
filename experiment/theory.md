There are several versions of the MIPS ISA and the one which we will be making use of in our assignments is a subset of MIPS32 Release 3. In particular our simulator supports only the MIPS CPU core instructions and these instructions are sufficient to do all the assignments. Please refer the document MIPS Architecure For Programmers, Volume I-A: Introduction to the MIPS 32 Architecture for more details.    


<img src="images/MIPSISAVersions.gif>


**Structure of an Assembly Language Program**  

Every assembly language program contains a Text Section (also called as Code Section) and an optional Data Section. In the Data Section we allocate memory to various program variables using Assembly Language Directives and in the Text Section we wrtie the assembly code which is a sequence of assembly language instructions to manipulate the data items declared in the Data Section. In High Level Programming Languages, a Compiler takes care of memory allocation to program variables by using the variable declarations like int a, b[10];, whereas in assembly the programmer has to do it explic;itly with the assistance of the assembler. The following is a sample MIPS program evaluating the expression varc = vara + varb where variables vara, varb and varc are integer.    


       // Data Section
       .data
       vara: .word 10      // initialize vara to 10
       varb: .word 20     // initialize varb to 20
       varc: .word        // No initial value specified for varc
       // Code Section
       .text
       lw $8, vara
       lw $9, varb
       add $10, $8, $9
       sw varc, $10 
       halt 
    	
 
**Writing if-then-else Code in MIPS**  

The following are the different kinds of Control-Abstractions provided by almost all high-level languages.  

1. goto statements.  
2. if-then-else statements  
3. Loop Constructs - do-while, for loops etc.    

All though any one of these Control Statements are sufficient to compute any function, a control statement in one form could be more appropriate in a particular situation than the others. For example, we could prefer a for-loop over a while-loop while iterating over array elements.    

MIPS ISA provides pc-relative conditional and unconditional branch instructions. Whereas the jump instructions use absolute addressing mode. Unlike other ISAs MIPS does not have a Condition Code register. So the MIPS ISA does not have CMP (compare) like instructions. MIPS ISA have branch delay slots and branch likely delay slots. The following is an example of how to convert an if-then-else construct into MIPS assembly.    

       // C-code
       if ( vara >= varb ) {
               varc = vara - varb 
        } 
        else {
         varc = vara + varb
        }

        // MIPS Code Fragment
        // Assume vara, varb, varc are signed integers residing in registers $r2, $r3 and $r4 respectively.  

              sub $1, $2, $3       # Store the result vara-varb in $r1 register. 
              bgez if
              nop                     # branch delay slot
              add $4, $1, $2       # compute vara+varb and store the result in $r4 register
              b exit
        if:  mov $4, $1            # Computing if-part
        exit:    	
 
**Implementing Loop Structures in MIPS ISA**  

Loops are an important form of control abstraction for programming. We have various kinds of loops like for, do-while, repeat-until etc. and each of these forms are suitable for a particular programming purpose. Any loop can be implemented using conditional and unconditional branch statements.  

The following is an example of a code segment illustrating how to translate loop structures into MIPS Assembly   

       // C-code
       sum = 0
       for( i = 0; i < 100; ++i ) 
          sum = sum + a[i];
       // MIPS Assembly
       // Data Section
       .data
       a .space 400      // allocate 400 bytes
       // Code Section. Assume index variable i is in register $r1 and sum is in register $r2.
       .text
               addi $1, $0, #100       // i = $r1 = 0
               xor $2, $2, $2         // sum = $r2 = 0
       loop:  la $3, a                 // $r3 = &a 
              lw $4, ($3)             // $r4 = a[i]
              add $2, $2, $4         // sum = sum + a[i]
              addi $3, $3, #4         // a = a + 4
              subi $1, $1, #1         // i = i - 1
              bgez $1, loop
              nop  
       	      halt 
    	    
