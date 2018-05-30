﻿#######
Verilog 
#######

Introduction
============

Verilog is a HDL and it is very similar to the C programming language and it was developed in 1985. Verilog became popular because it is easy to learn, if you have some programming experience with C, you can describe the system in a sequential or in a combinational way and the most popular tools to develop digital systems support Verilog.

In Verilog the system is described with inputs, outputs and modules that implement some logic function. The designer will implement modules and the software will optimize and implement the system to use less logic cells as possible, in Red Pitaya case the software is Vivado. Modules can be implemented inside other modules, a module output can be another module input. A module is declared using the words **module** and **endmodule**, the function, the inputs and outputs are declared inside it. Some characteristics of Verilog are:

- It is case sensitive, for example an input named **adc_in** is different than an input named **Adc_in**.
- All words of Verilog language itself like module are in lowercase.
- The semicolon is used to end a line of code.
- Line comments are made with **// code**, and block comments with **/* code block */**.

Verilog Example
===============

Next there is an example of a project that multiplies two inputs with 18 bits resulting in an output with 36 bits. First is created a module named **projtest** and inside parenthesis is declared the input and output ports. The // are a comment so the line of code is invisible to the compilation. Next it is assigned to the output the mathematical multiplication of the two inputs.

.. code-block:: Verilog
    
    module projtest(
        input [17:0] in_a,
        input [17:0] in_b,
        output [35:0] out_f
    );
    //   design_1 instanciation1( .input_a(in_a), .input_b(in_b), 
    .clk(clock), .outp(out_f)  );
    assign out_f = in_a * in_b;

    endmodule

Port Types
==========

The port types can be, **input**, **output** and **inout**.

Data Types
==========

There are two types of data in Verilog, one is called **net** and the other is called **reg**.  A reg declaration is used to store some temporary data and a net is used to connect blocks and processes. 

Net
---

Net declarations can be **wire** , **tri**, **supply0** and **supply1**. 

=======   ===============================
wire      represents a node or connection
tri       represents a tri-state node
supply0   represents the logic 0
supply1   represents the logic 1
=======   ===============================

Reg
---

Reg declarations can be **reg** , **integer**, **time** and **realtime**. A variable of type reg can be designated only by a procedure statement, task, or function. A variable of type reg cannot be the output of a port or an **assign** statement.

Data input output rules
=======================

If you have a variable of type net, it can be declared as **input**, **output**, or **inout**. A variable of type register can only be declared of type **output**.