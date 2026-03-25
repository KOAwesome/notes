	

|     | if ( fast == null ) {<br><br>// if n == length just remove head move one step<br><br>return head.next;<br><br>} |
| --- | --------------------------------------------------------------------------------------------------------------- |
|     | its direct just loop and add node                                                                               |

| Problem               | Pattern               | Trigger                        | Core                                                                               | Return vs Global | Mistake I Made                                  |
| --------------------- | --------------------- | ------------------------------ | ---------------------------------------------------------------------------------- | ---------------- | ----------------------------------------------- |
| nth node from the end | fast and slow pointer | linkedlist movement            | - move fast n nodes<br>- slow points n+1 th node from end                          |                  | - i moved fast till mid. i need to move n nodes |
| k lists merge         | dummy                 | linkedlist multiple operations | - add linkedlists that are empty to hashset <br>- keep adding the smallest element |                  |                                                 |
|                       |                       |                                |                                                                                    |                  |                                                 |
