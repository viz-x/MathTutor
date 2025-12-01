==============================
COMAL-80 Math Tutor
==============================

A Classic 1980s Educational Program

.. image:: https://img.shields.io/badge/Language-COMAL--80-blue
   :alt: Language

.. image:: https://img.shields.io/badge/Platform-C64%20%7C%20BBC%20%7C%20CP%2FM-green
   :alt: Platform

Overview
========

An authentic COMAL-80 math practice program for vintage computers. Help students practice arithmetic with interactive questions and immediate feedback.

**File:** ``mathtutor.lst``

**Lines:** 210 (numbered 0010-2100)

Features
========

* **Four Operations:** Addition, Subtraction, Multiplication, Division
* **Adaptive Difficulty:** Starts easy (1-10), increases to 1-25
* **Score Tracking:** Percentage and performance feedback
* **Random Praise:** 5 encouraging messages
* **10 Questions** per session

Quick Start
===========

1. Save code as ``mathtutor.lst``
2. Load into COMAL-80 emulator
3. Type ``RUN``

Compatible Platforms
====================

* Commodore 64 (with COMAL-80 cartridge/disk)
* BBC Micro (with COMAL installed)
* CP/M systems (with COMAL-80 interpreter)

How to Run
==========

Commodore 64 (VICE Emulator)
-----------------------------

1. Download VICE: https://vice-emu.sourceforge.io/
2. Attach COMAL-80 cartridge or disk image
3. Type the program or ``LOAD "MATHTUTOR"``
4. Type ``RUN``

BBC Micro (BeebEm)
------------------

1. Download BeebEm: http://www.mkw.me.uk/beebem/
2. Install BBC COMAL ROM
3. Load program
4. Type ``RUN``

CP/M Systems
------------

1. Boot CP/M-80
2. Run COMAL interpreter: ``COMAL``
3. Load: ``LOAD MATHTUTOR.LST``
4. Run: ``RUN``

Sample Session
==============

::

    ================================
          M A T H   T U T O R      
    ================================

    SELECT AN OPERATION:

      1 - ADDITION
      2 - SUBTRACTION
      3 - MULTIPLICATION
      4 - DIVISION
      5 - QUIT

    YOUR CHOICE: 1

    ANSWER 10 PROBLEMS

    QUESTION 1:
    5 + 6 = ?
    YOUR ANSWER: 11
    CORRECT!

    QUESTION 2:
    9 + 7 = ?
    YOUR ANSWER: 17
    INCORRECT. THE ANSWER IS 16

    ...

    ================================
          FINAL SCORE REPORT       
    ================================

    YOU ANSWERED 8 OUT OF 10
    PERCENTAGE: 80%

    VERY GOOD! KEEP IT UP!

    ================================

Commands
========

Save Program
------------

.. code-block:: comal

    SAVE "MATHTUTOR"

Load Program
------------

.. code-block:: comal

    LOAD "MATHTUTOR"
    RUN

List Code
---------

.. code-block:: comal

    LIST          // Entire program
    LIST 0740-    // From line 740
    LIST -1000    // Up to line 1000

Customization
=============

Change Number of Questions
---------------------------

Line 0820:

.. code-block:: comal

    FOR question%:=1 TO 10 DO    // Change 10 to desired number

Adjust Starting Difficulty
---------------------------

Line 0770:

.. code-block:: comal

    maxval%:=10    // Try 5 (easier) or 15 (harder)

Modify Difficulty Increase
---------------------------

Lines 1200-1210:

.. code-block:: comal

    IF correct%>=3 AND maxval%<25 THEN    // After 3 correct
      maxval%:=maxval%+5                   // Increase by 5

Technical Details
=================

COMAL-80 Syntax
---------------

* ``//`` for comments (not ``REM``)
* ``:=`` for assignment (not ``=``)
* ``PROC``/``ENDPROC`` for procedures
* ``IF...ELIF...ELSE...ENDIF`` blocks
* ``FOR...DO...ENDFOR`` loops
* ``REPEAT...UNTIL`` loops

Random Numbers
--------------

.. code-block:: comal

    RND(10)      // Returns 0-9
    RND(10)+1    // Returns 1-10 (used in program)
    RND(5)+1     // Returns 1-5 (for praise)

Key Variables
-------------

============  ====================================
Variable      Purpose
============  ====================================
mode%         Selected operation (1-5)
correct%      Number of correct answers
total%        Total questions asked
num1%, num2%  Random numbers for problem
answer%       User's answer
result%       Correct answer
maxval%       Maximum value (difficulty level)
percent%      Score percentage
============  ====================================

Main Procedures
---------------

=====================  ========================================
Procedure              Description
=====================  ========================================
initialize             Setup and seed random generator
show_menu              Display operation menu
run_session(mode%)     Run 10-question practice
ask_question(...)      Display math problem
calculate_result(...)  Compute correct answer
praise                 Show random encouragement
show_score             Display final report
=====================  ========================================

Troubleshooting
===============

**"SYNTAX ERROR"**
    Verify you're using COMAL-80, not BASIC

**Program won't RUN**
    Check all ``PROC`` have matching ``ENDPROC``

**Numbers too large**
    Some implementations limit integers to 32767

**Division errors**
    Program ensures clean division automatically

Educational Goals
=================

This program helps students:

* Practice mental arithmetic
* Build confidence with positive feedback
* Experience adaptive difficulty
* Track improvement with percentages
* Enjoy learning through interaction

File Extensions
===============

Use ``.lst`` extension for COMAL-80 source files:

* ``mathtutor.lst`` - Standard listing format
* ``mathtutor.cml`` - Alternative COMAL extension
* ``mathtutor.txt`` - Plain text (rename to .lst)

License
=======

Public Domain - Free for educational use

Credits
=======

Created as authentic 1980s educational software recreation.

Compatible with original COMAL-80 implementations.

**Happy Computing!** 🎓

----

*For best results, use actual vintage hardware or accurate emulators.*
