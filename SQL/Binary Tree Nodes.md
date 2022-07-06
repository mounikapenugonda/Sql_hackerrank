### Binary Tree Nodes
You are given a table, BST, containing two columns: N and P, where N represents the value of a node in Binary Tree, and P is the parent of N.
| column | type|
| -- | -- |
| n | integer |
| p | integer |

Write a query to find the node type of Binary Tree ordered by the value of the node. Output one of the following for each node:

Root: If node is root node.
Leaf: If node is leaf node.
Inner: If node is neither root nor leaf node.
Sample Input ::
|N |P |
| --| -- | 
|1	|2|
|3	|2|
|6	|8|
|9|	8|
|2	|5|
|8	|5|
|5|	NULL |

Sample Output ::
1 Leaf
2 Inner
3 Leaf
5 Root
6 Leaf
8 Inner
9 Leaf

Explanation ::
The Binary Tree below illustrates the sample:
#
        5     
    2         8
1       3   6     9

    Solution: SELECT N,CASE
                        WHEN P IS NULL THEN 'Root'
                        WHEN N IN (SELECT P FROM BST) THEN 'Inner'
                        ELSE 'Leaf'
                        END
              FROM BST ORDER BY N;

        EXplanation : line by line
            SELECT N                                        -- it will give values of N
            CASE                                           -- it is like if -then - else 
                WHEN P IS NULL THEN 'Root'                 -- when p is null it will treat that as root node
                WHEN N IN (SELECT P FROM BST) THEN 'Inner' -- when the N value present/ matches in P = inner node
                ELSE 'Leaf'                                -- else all are nodes - leaf
            END
            FROM BST ORDER BY N;                            -- from the table name with order of N values.
