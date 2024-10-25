# Numerical-methods-2107049
Functions with description:
1->Upper_triangular(): This function turns input matrix into an upper triangular matrix and returns the resultant matrix.The function works by finding max row and swaping with current row and doing row operations. Row operations happens between current row and those rows below it.The goal is to make all elements below diagonal elements 0(Forward elimination) .Thus we find an upper triangular matrix.The algorithm: 

For each row k from 0 to n-1:
Partial pivoting: find row i where(i>k) |arr[i][k]|>|arr[k][k]|
swap row i with row k.
for each row i from row k+1 to n-1:
calculate factor f=arr[i][k]/[k][k].
Subtract f times row k from row i for each element in row i .
return matrix arr

2->Reduced_row_echelon(): This function turns input matrix into Reduced row echelon form.Meaning, only diagonal elements are 1 and rest entries are 0.To do this  we first turn our input matrix into Upper triangular matrix using Upper_triangular().Then, we follow steps similar to Upper_triangular(), excluding partial pivoting. The steps of row operations will be reverse order of Upper_triangular() i.e. backward elimination. After that each row is divided by corresponding row's diagonal element.

3->Solvable(): This function returns boolean data indicating wheather the input matrix representing system of linear equations are solvable or not. This is determined by 2 questions-
  1.Are there as many equations as the number of variables?
  2.Are there any 0 in the diagonal after making the matrix upper triangular?
If 1 is "no" then equations are unsolvable. If 2 is "Yes" then the equations are unsolvable. Otherwise they are solvable.

4->Invertible():This function returns boolean data indicating wheather input matrix is invetible or not.This is determined by 2 questions-
  1.Is row number = column number?
  2.Are there any 0 in the diagonal after making the matrix upper triangular?
  If 1 is "no" then equations are unsolvable. If 2 is "Yes" then the equations are unsolvable. Otherwise they are solvable.

5->Gauss_elimination(): Solves solvable system of linear equations. Firstly upper triangular matrix is made using Upper_triangular() with input matrix as input. Then the solutions are found by back substitution.
Back-Substitution (Solve for Variables):
   - Initialize the solution vector x as an array of zeros.
   - For each row i from n-1 down to 0:
     - Calculate x[i] by dividing the modified augmented term A[i][n] by A[i][i], then subtract the results of all known x[j] values for j > i from A[i][n] to isolate x[i].

6->Gauss_jordan_elimination():Solves solvable system of linear equations. Firstly Reduced row echelon matrix is made using Reduced_row_echelon() with input matrix as input.The last column of the resultant matrix(augmented part) is our solution.

7->Matrix_inversion():Inverts Invertable matrices.Firstly the input matrix is augmented with its corresponding identity matrix. Then the resultant matrix is turned into reduced row echelon form using Reduced_row_echelon().The augmented part of the resultant matrix is the inverse of the input matrix.

The main function uses the functions above to make  a user friendly console application.

  
  
