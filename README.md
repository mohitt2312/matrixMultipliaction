# Matrix Multiplication using Hadoop MapReduce

This project implements matrix multiplication using the Hadoop MapReduce framework. The project consists of three main components: a driver class (`MatrixMultiply`), a mapper class (`Map`), and a reducer class (`Reduce`). The input matrices are expected to be provided in a specific format, and the output will be the product of these matrices.

## Project Structure

- **MatrixMultiply.java**: The driver class that sets up the Hadoop job configuration and specifies the mapper and reducer classes.
- **Map.java**: The mapper class that processes each line of the input files and emits intermediate key-value pairs.
- **Reduce.java**: The reducer class that takes the intermediate key-value pairs and performs the matrix multiplication.

## Prerequisites

- Java JDK 8 or higher
- Apache Hadoop 2.7.1 or higher
- Apache Maven 3.6.3 or higher (for building the project)

## Input Format

The input files should contain the matrices in the following format:

For matrix M:
M,i,j,Mij
For matrix N:
N,j,k,Njk

Here, `i`, `j`, and `k` are the row and column indices, and `Mij` and `Njk` are the values of the matrix elements.

### Input

Matrix M (`1.txt`):
M,0,0,1
M,0,1,2
M,1,0,3
M,1,1,4


Matrix N (`2.txt`):
N,0,0,5
N,0,1,6
N,1,0,7
N,1,1,8

## Output Format

The output will be in the format:
i,k,value
Where `i` and `k` are the row and column indices of the resulting matrix, and `value` is the computed value for that cell.

### Output

For the given input, the output will be:
0,0,19.0
0,1,22.0
1,0,43.0
1,1,50.0
### create a JAR file in the target directory
To run the Hadoop job, use the following command:
hadoop jar target/MatrixMultiply.jar MatrixMultiply input/* output/
## License
This project is licensed under the MIT License - see the LICENSE file for details.

Feel free to customize the content according to your specific needs and project details.
