# NLA_final

## 🔧 Build

Codes: 

```bash
mkdir build && cd build
cmake ..
cmake --build .
# run the tests
# ./main
```

Documents:

```bash
cmake --build . --target doc
```

## ▶ Run

Usage `#include "HermitianEigenSolver.h"`

Example:

```c++
arma::cx_mat A = arma::randn<arma::cx_mat>(5, 5);
A = arma::symmatl(A);
HermitianEigenSolver hes(A, false); // eigenvalues only
hes.eigenvalues().t().print("The eigenvalues of A are:");
hes.compute(A + arma::eye(5, 5)); // re-use hes for A+I
hes.eigenvalues().t().print("The eigenvalues of A+I are:");
```

Output:

```
The eigenvalues of A are:
   3.7758  -1.8090  -1.2123   1.2705   0.6426
The eigenvalues of A+I are:
   4.7758  -0.8090  -0.2123   2.2705   1.6426
```

