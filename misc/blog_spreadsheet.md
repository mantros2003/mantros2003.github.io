# Making a terminal-based spreadsheet application
In this short blog, I will be documenting my process of building a command-line spreadsheet application. This blog will cover general things that I learn about spreadsheets while building the project and things like why I take certain decisions, the datastructures I use, better ways of implementing a functionality.

## Why spreadsheet
Because I have to build a spreadsheet in one of my courses. However, I wish to continue building this project as a way to learn more about a technology that is being used by milions of people.

## Why blog
I am writing a blog to better organize what I learn during this project. Also, I hope this helps me in improving my writing skills.

## Begin
### The cell
A spreadsheet is just a table or a 2 dimensional grid that stores values at each cell. A cell is the basic data structure upon which a spreadsheet is built. In commercial softwares like MS Excel, each cell can contain a wide variety of data types, like integer, floats, strings, date-times, and support complex functions and references to other cells in the same workbook, to some other sheet, or even another document. My implementation would be very very basic. To keep things simple, it would only support integers. There would be some basic fucntions like MIN, MAX, AVG and we would also add support for references.\
We would represent the cell using a struct. The cell needs to store an integer.
```c
struct cell {
  int data;
};
```
*This is not the final version of the struct. We would update and improve it as we code.*
