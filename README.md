# DAA-Questions

## Question 1
Problem Statement - If two people hate each other those two friends will not be invited. maximize the number of people that can attend

## Greedy Solution
## Algorithm

The approach idea is to start with the friends who have less enemies so that we can maximize the total number of friends that can attend

so first we sort the sublists based on the length of sublists(from small to big).Then we take the first element and add it to the invite list then we add the elements enemies to hated list so that when the elements in hated list comes up we can skip them. In this way we iterate through all the sublists.

## test cases
in the list first digit signifies the the person and the remaining are his enemies
[[1,2,3,4],[2,1,5,6,7],[3,1,5,6,7],[4,1,5,6,7],[5,2,3,4,6,7],[6,2,3,4,5,7],[7,2,3,4,5,6]] - Greedy doesnt work
[[0,1,3],[1,0,2],[2,1],[3,4],[4,1]]-both greedy and backtracking work

## Back Tracking
## Algorithm

We can use backtracking to solve the problem

The basic approach is before you add a element you check if there is any other element already present in the invite list that has the current element that is about to be added as an enemy. Then you make two backtracking calls one with tha current element and one without, if the validd function did not satisfy you run a backtracking call with the element. In this way we will be covering the combination from (1,2.....)(1,3.....)..... till (7,2.....).


## Question 2
Problem Statement - Implement n-queen problem using backtracking approach for n = 4 to 8 and trace space tree till 3 valid solutions

## Algorithm

In N-queen problem the base condition is when the rows are equal to n and also if we get 3 optimal solutions we can stop it(given in question).we use three sets columns,ldiag,rdiag - when you take indices in the diagonals like (2,1),(3,2),(4,1) when you perform (row - column) the elements in that diagonal give the same value all diagonals in this orientation in a table from left top to right bottom orientation and when th other way{(2,4),(3,3),(4,2)} is taken that is from right top to left bottom whne you perform (row+column) th ediagonal elements give the same values so with this we can figure out if a diagonal is used or not like we do for columns.

Then iterate through each column and check if the elements are in the sets(column,ldiag,rdiag) then we add the current value of column at make a backtracking call and at the location where all condition satisfies we put 'Q' and without the current column values we make a backtracking call
