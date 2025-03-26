## The cell
A spreadsheet is just a table or a 2 dimensional grid that stores values at each cell. A cell is the basic data structure upon which a spreadsheet is built. In commercial softwares like MS Excel, each cell can contain a wide variety of data types, like integer, floats, strings, date-times, and support complex functions and references to other cells in the same workbook, to some other sheet, or even another document. My implementation would be very very basic. To keep things simple, it would only support integers. There would be some basic fucntions like MIN, MAX, AVG and we would also add support for references.\
We would represent the cell using a struct. The cell needs to store an integer.
```c
struct cell {
  int data;
};
```
*This is not the final version of the struct. We would update and improve it as we code.*
