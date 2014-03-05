Windows Programming Laboratory Work #1
======================================

Title
-----
Window. Window handling. Basic window’s form elements.

Introduction
------------
Main purposes of this lab work:
* Understand Event-Driven Programming.
* Study Win32 API.

Secondary purposes of this lab work:
* Use a Version Control Systems (GIT).
* Write code according to a Programming Style Guide.

Mandatory Objectives
--------------------
* Create a Windows application
* Choose Programming Style Guidelines that you'll follow
* Add 2 buttons to window: one with default styles, one with custom styles (size, background, text color, font family, font size)
* Add 2 text inputs to window: one with default styles, one with custom styles (size, background, text color, font family, font size)
* Add 2 text elements to window: one with default styles, one with custom styles (size, background, text color, font family, font size)

Objectives With Points
----------------------
* Make elements to fit window on resize. **(1 pt)**
* Make elements to interact or change other elements. **(2 pt)**
* Change behavior of different window actions (at least 3). **(1 pt)**
* Write your own PSG. **(1 pt)**

Programming Style Guide
-----------------------
For this laboratory work, I was inspired by [Rhombus C style guide](https://github.com/nickbjohnson4224/rhombus/wiki/C-style-guide). 
But introduced some changes that make me feel more comfortable while typing the code.

*Introduction

I will mention the most important differences adopted for my particular programming style.

*Win32 API specifics

Naming should follow the [Hungarian notation](http://en.wikipedia.org/wiki/Hungarian_notation) convention (Systems Hungarian notation is preferable to
Apps Hungarian notation).

Calls to functions with multiple arguments (more than 3), should have each argument on a separate line. However, for functions that are called very often
(such as MessageBox(), DrawText(), SendMessage(), etc.), it is acceptable to call these functions on a single line. Arguments referring to similar things, such as
`nHeight` and `nWeight`, or pairs of coordinates (x & y), `NULL`, can share the same line. 
```C
CreateWindowEx(
      (DWORD)NULL,
      TEXT("button"),
      TEXT("Quit"),
      WS_CHILD | WS_VISIBLE | BS_PUSHBUTTON | BS_OWNERDRAW,
      220, 260,
      60, 20,
      hwnd,
      (HMENU)IDC_QUIT_BUTTON,
      hProgramInstance,
      NULL);
```
Also, control statements requiring curly brace blocks have the opening brace on the next line as the statement:
```C
statement 
{
    ... code ...
}
```
So that braces will show the beginning and the end of the statement. 

Application Creation Steps
--------------------------
In this laboratory work I created an application that has two buttons, two boxes for inputing the text, 2 strings and a message box. I consulted the book "Programming Windows, 5th Edition", by Charles Petzold, guidebook for laboratory works and Internet. 
I worked in two parts of code: the procedure WndProc and WinMain. In WinMain is registered the class, created the window and is run the message loop. In WndProc are processed the messages that are passed from WinMain.
The messages are processed in the way that the close button (x) plays a sound, maximize button closes the window, minimize button moves the window in the left top corner of the screen and displays a message box. The button Send displays the message box with text "Message was sent", the button Cancel quits the program.

Result Application
------------------
This is a screenshot of the application in the Windows 7 environment:

![Screenshot]()

Conclusions
-----------

After finishing the laboratory work, I learned how the elements of the window are created, how their behavior can be changed. I worked with messages, understood how the elements and their actions are interconnected. This concepts can be applied not only in windows programming, but also in another systems programming. 
