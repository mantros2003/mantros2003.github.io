## The cell
A spreadsheet is just a table or a 2 dimensional grid that stores values at each cell. A cell is the basic data structure upon which a spreadsheet is built. In commercial softwares like MS Excel, each cell can contain a wide variety of data types, like integer, floats, strings, date-times, and support complex functions and references to other cells in the same workbook, to some other sheet, or even another document. My implementation would be very very basic. To keep things simple, it would only support integers. There would be some basic fucntions like MIN, MAX, AVG and we would also add support for references.\
We would represent the cell using a struct. The cell needs to store an integer.
```c
struct cell {
  int data;
};
```
*This is not the final version of the struct. We would update and improve it as we code.*

This is a very basic cell. We currently don't have any means of storing relations between cells. To store these informations, we need to add a field to store relations. We can store pointers to the cells that are *related* to the cell. We will store two lists of pointers, one for the cells that depend on cell, other for the cells that are influenced by the cell. For e.g. cell A1 depends on B1 as A1=B1+1, and C1 depends on A1 as C1=A1+1, then struct for A1 would look like:
```
A1 {
  data: 10
  out_deps=[pointer to C1]
  in_deps=[pointer to B1]
}
```
As C standard library does not provide us with any implementation for dynamically sized list, we can make our own linked list. Linked list would be just fine for out work as we don't need constant time lookup. O(n) to retrieve link at an index would not be an issue for our work.\
A linked list is a very basic data structure that is made up of nodes that contain some data and link to the next node.
We will define a linked list node which will contain a pointer to a cell and a pointer to the next node.
```c
struct linked_list {
  struct cell *cell_ptr;
  struct linked_list *next;
};
```
We will add pointers to two linked list in our cell struct.
```c
struct cell {
  int data;
  struct linked_list *in_deps;
  struct linked_list *out_deps;
};
```
