# Sparse Matrix Implementation

## Overview
This project implements a Sparse Matrix data structure and operations in JavaScript. It's designed to efficiently handle large matrices with many zero elements by only storing non-zero values. The implementation supports basic matrix operations such as addition, subtraction, and multiplication.

## Features
- Efficient storage of sparse matrices
- Matrix addition
- Matrix subtraction
- Matrix multiplication
- Reading matrix data from a string (simulating file input)
- Printing matrix contents

## Requirements
- Node.js (version 12.0 or higher recommended)

## Installation
1. Clone this repository or download the source code.
2. Navigate to the project directory.
3. There are no additional dependencies to install.

## Usage
To use the SparseMatrix class in your project:

1. Import the SparseMatrix class into your JavaScript file:
   ```javascript
   const SparseMatrix = require('./SparseMatrix');
   ```

2. Create a new SparseMatrix instance:
   ```javascript
   // From dimensions
   const matrix = new SparseMatrix({ rows: 3, cols: 3 });

   // Or from a string representation
   const matrixString = `
   rows=3
   cols=3
   (0, 0, 1)
   (1, 1, 2)
   (2, 2, 3)
   `;
   const matrix = new SparseMatrix(matrixString);
   ```

3. Perform operations:
   ```javascript
   const matrix1 = new SparseMatrix(matrixString1);
   const matrix2 = new SparseMatrix(matrixString2);

   const sum = matrix1.add(matrix2);
   const difference = matrix1.subtract(matrix2);
   const product = matrix1.multiply(matrix2);

   sum.print();
   ```

## Example
Here's a simple example of how to use the SparseMatrix class:

```javascript
const matrix1String = `
rows=3
cols=3
(0, 0, 1)
(1, 1, 2)
(2, 2, 3)
`;

const matrix2String = `
rows=3
cols=3
(0, 0, 2)
(1, 1, 3)
(2, 2, 4)
`;

const matrix1 = new SparseMatrix(matrix1String);
const matrix2 = new SparseMatrix(matrix2String);

console.log("Matrix 1:");
matrix1.print();

console.log("\nMatrix 2:");
matrix2.print();

console.log("\nAddition Result:");
const addResult = matrix1.add(matrix2);
addResult.print();
```

## Input Format
The input string for creating a matrix should follow this format:
- First line: `rows=<number_of_rows>`
- Second line: `cols=<number_of_columns>`
- Subsequent lines: `(<row>, <column>, <value>)` for each non-zero element

## Error Handling
The implementation includes basic error handling for:
- Invalid input formats
- Matrix dimension mismatches in operations
- Out-of-bounds element access

## Limitations
- The current implementation assumes all input values are integers.
- Very large matrices might face performance issues due to JavaScript's memory limitations.

## Future Improvements
- Implement more advanced matrix operations (e.g., transpose, determinant)
- Optimize for better performance with very large matrices
- Add support for floating-point values
- Implement file I/O for direct reading from and writing to files

## Contributing
Contributions to improve the implementation or add new features are welcome. Please feel free to submit pull requests or open issues for bugs and feature requests.

## License
This project is open source and available under the [MIT License](https://opensource.org/licenses/MIT).
