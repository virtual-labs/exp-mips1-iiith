1. Write MIPS Assembly Language Programs computing the following expressions or program segments.

    1. Variables are of type unsigned integers and word sized. Also the variables b, c, d and e are initialized to values 10, 20, 30 and 40 respectively.  

        a = (b + c) - (d + e)  

    2. Variables are of type signed integers and half-word sized." "Variables b, c, d and e are initialized to values -10, 20, 30 and -40 respectively.  

        a = (b + c) - (d + e)  

    3. Variables are of type unsigned integers and word sized. Also the variables b, c, d and e are initialized to values 10, 20, 30 and 40 respectively.  

        b = a + 256 .  
        c = b - 0xfffff  
        a = (b + c) - (d + e + 0xffffe)  

    4. Dot Product of two signed half-word sized integer array vectors A and B each of dimension 5. The resultant dot-product value should reside in the register $r1 by the end of computation.  

    5. A and B are two unsigned word-sized integer array vectors each of size dimension 5. Compute the following expression.  

        CONV = A[0] * B[4] + A[1] * B[3] + A[2] * B[2] + A[3] * B[1] + A[4] * B[0]  

 

2. Write MIPS Assembly Language Programs equivalent to the following C-code fragements.

     1. if ( a < b) {         // a and b are signed integers  
           c = a - b;  
        }  

     2. if ( a < b) {         // a and b are unsigned integers  
           c = a - b;  
        }  

     3. if ( a < -1234) {         // a is a signed integer  
           a = 4 * a ;  
        }  
        else {  
           a = a/4;  
        }  

     4. if ( a < b ) {         // a, b, c are unsigned integer  
           if ( a < c) {  
              min = a;  
           }  
          else { min = b < c ? b : c; }  
        }  
        else {  
          min = b < c ? b : c  
        }  

.

3. Write MIPS Assembly Language Programs equivalent to the following C-code fragments..  
   
     1. sqrsum = 0;  
       	 for( i = 0 ; i < 100; ++i)  
            sqrsum = sqrsum + a[i] * a[i];  

     2. convsum = 0;  
        for ( i = 0, j = 99; i <100; ++i, --j )  
              convsum += a[i] * b[j] ;  

     3. sum = 0;  
        for( i = 0 ; i < 100; ++i)  
            for( j = 0; j < 100; ++j)  
                 sum = sum + a[i, j] ;  

