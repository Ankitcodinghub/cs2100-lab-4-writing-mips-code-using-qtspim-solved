# cs2100-lab-4-writing-mips-code-using-qtspim-solved
**TO GET THIS SOLUTION VISIT:** [CS2100 Lab #4: Writing MIPS code using QtSpim Solved](https://www.ankitcodinghub.com/product/cs2100-computer-organisation-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;114523&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS2100 Lab #4: Writing MIPS code using QtSpim Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
[ This document is available on LumiNUS and module website http://www.comp.nus.edu.sg/~cs2100 ]

Name: ________________________________ Student No.: ____________________

Lab Group: _____

Objective

In this lab, you will use QtSpim to understand how typical programs are written. This document and its associated files (messages.asm and arrayCount.asm) is provided in the ZIP file and can also be downloaded from the CS2100 module website.

Reading and Writing Message to Console Window: messages.asm

Recall that in Lab #3 sample2.asm, you made use of the system call (syscall) to print some text. SPIM provides a small set of operating-system-like services through the system call

(syscall) instruction (see Appendix A, pages A-43 to A-45).

To request a service, a program loads the system call code into register $v0 and arguments into registers $a0 – $a3 (see Figure A.9.1 below). System calls that return values put their results in register $v0. For this lab, we are interested in only the following system calls: print_string, print_int, read_int and exit.

For example, the following code in messages.asm prints “the answer = 5”.

# messages.asm .data

str: .asciiz “the answer = ”

.text main: li $v0, 4 # system call code for print_string la $a0, str # address of string to print syscall # print the string

li $v0, 1 # system call code for print_int li $a0, 5 # integer to print syscall # print the integer

li $v0, 10 # system call code for exit syscall # terminate program

The print_string system call (system call code 4) is passed a pointer (memory address) to a null-terminated string, which it writes to the console. The print_int system call (system call code 1) is passed an integer and it prints the integer on the console. The exit system call (system call code 10) indicates the end of the program.

The li (load immediate) and la (load address) are pseudo-instructions (refer to Lab #3).

Run the above program to verify your understanding.

Modify messages.asm and call the new program task1.asm. The modified program should read the value to be printed from the console before printing the value. The system call read_int reads an entire line of input up to and including the newline. Characters following the number are ignored. Note that read_int modifies the register $v0 (where you put the code for system call) as it returns the integer value in register $v0.

The following screen capture shows a run of the program. The first line is your input, and the second line is the output of your program.

First, let us learn about allocating memory space for variables in a program. The assembler directive “.data” allows us to reserve memory space in the data segment. These reserved locations are used to store the values of various program variables during program execution.

Key idea: Values of program variables are stored in the memory. We load them into registers (perform a mapping) only when we want to manipulate or access them during execution.

Count the number of multiples of X in a given array of 8 non-negative numbers, where X is a user chosen power-of-two value, e.g. 1, 2, 4, 8, ….

Use arrayCount.asm in the zip file or download it from the module website. The initial content of the file is:

# arrayCount.asm .data

arrayA: .word 1, 0, 2, 0, 3 # arrayA has 5 values count: .word 999 # dummy value

.text main:

# code to setup the variable mappings

add $zero, $zero, $zero # dummy instructions, can be removed

…………

# code for reading in the user value X

# code for counting multiples of X in arrayA

# code for printing result

# code for terminating the program

li $v0, 10 syscall

The main routine contains several dummy instructions (instructions with no real effect) so that you can step through the program to observe the content in the data segment.

Where is the array arrayA located in the data segment? Give the base address (starting address) of the array:

arrayA is at 0x______________________

Where is the program variable count in the data segment?

count is at 0x_______________________

(Hint: Don’t forget that 999 is in decimal…)

The given code only allocates 5 elements for arrayA. Enlarge the array to size 8. You can place any valid integer values for the new locations. Fill in the assembler directive below:

arrayA: ____________________________________

Now, let us perform the following mappings:

Base address of arrayA ➔ $t0 (similar to notation used in lectures) count ➔ $t8

To map arrayA: _____________________

_____________________

To map count : _____________________

_____________________

We are almost ready to tackle the task. One last obstacle is to figure out how to check for “Multiples of X, where X is a power-of-two”. Recall that in Tutorial #2 Q3a, we learned that “andi” instruction can be used to find the remainder of division by 16. For the following questions, give the correct mask for the andi instruction to compute “$t4 = $t3 % X”.

If X is 32, andi $t4, $t3, 0x______

If X is 8, andi $t4, $t3, 0x______

Observe that we can easily generate the mask from X. If X is stored in register $t8, complete the following instruction to generate the mask in register $t5. (Hint: look at the mask as a number).

______ $t5, $t8, ______ (fill in the operation and the last operand)

We are now ready to finish off the task. Write the necessary code to:

a. Read user input value, X. You can assume X is always a power-of-two integer, i.e. there is no need to check for invalid user input.

b. Count the number of multiples of X in arrayA and print the result on screen.

Try to use different values in your code to test. Also, please make sure the “count” value is properly recorded in the data segment at the end of execution.

This is a follow-up task on task 2. First, make a copy of your solution in task 2 and name it

“inputArrayCount.asm”.

Your task is very “simple” – add code to read 8 values from the user and store them in the array arrayA. Then print the number of multiples of X found (where X is a power-of-two also entered by the user). By reusing your code in task 2, you only need to add a couple of new instructions. Below is a sample run:

Notes: You should prepare your programs before the lab. Your labTA will mark your work in your presence. You do not need to submit any program. Please do not send your programs to your labTA after the lab; they will not be accepted.
