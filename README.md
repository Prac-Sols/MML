### Q1. Partial Derivative:

```python

    import sympy as sp
    
    # Defining the variables:
    x, y = sp.symbols('x, y')
    
    # Deifining the function:
    f = x**2 * y + sp.sin(x*y)
    
    # Computing the partial derivatives:
    partial_x = sp.diff(f, x)
    partial_y = sp.diff(f, y)
    
    # Printing the results:
    print("Function:", f)
    print("Partial derivative with respect to x:", partial_x)
    print("Partail derivative with respect to y:", partial_y)

```


### Q2. Solve System of Linear Equations

```python

    import numpy as np
    
    # Defining the system of linear equations:
    # example: 2x + 3y = 8 and 3x + 4y = 11
    A = np.array([[2, 3], [3, 4]])
    B = np.array([8, 11])
    
    # Solving the system of equations:
    solution = np.linalg.solve(A, B)
    
    print("Solution:")
    print(f"x = {solution[0]}")
    print(f"y = {solution[1]}")

```


### Q3. Dot Product and Cross Product of Vectors

```python

    import numpy as np
    
    def dot_product(v1, v2):
        return np.dot(v1, v2)
    
    def cross_product(v1, v2):
        return np.cross(v1, v2)
    
    # Example usage:
    V1 = np.array([1, 2, 3])
    V2 = np.array([4, 5, 6])
    dot_prod = dot_product(V1, V2)
    cross_prod = cross_product(V1, V2)
    
    print("Dot product:", dot_prod)
    print("Cross product:", cross_prod)

```


### Q4. Simpson's One-Third Rule

```python

    def simpsons_one_third(x, y):
        n = len(x) - 1
    
        if n % 2 != 0:
            raise ValueError("Number of intervals must be even")
        
        h = (x[-1] - x[0]) / n
        
        integral = y[0] + y[-1]
        for i in range(1, n, 2):
            integral += 4*y[i]
    
        for i in range(2, n-1, 2):
            integral += 2*y[i]
    
        integral *= h/3
    
        return integral
    
    # Example usage:
    x = [0, 1, 2, 3, 4]
    y = [1, 2, 0, 2, 1]
    
    integral = simpsons_one_third(x, y)
    
    print("Integral =", integral)
```


### Q5. Simplex Method

```python

    from scipy.optimize import linprog
    
    # Coefficients of the objective funtion (to be minimized):
    c = [-1, -2]
    
    # Coefficients of the inequalities (left-hand side):
    A = [[1, 1], [-1, 2]]
    
    # Right-hand side of the inequalities:
    b = [5, 4]
    
    # Solving the linear programming problem:
    result = linprog(c, A_ub = A, b_ub = b, method='simplex')
    
    if result.success:
        print("Optimal value:", -result.fun)
        # Convert back to maximization problem:
        print("x: ", result.x[0])
        print("y:", result.x[1])
    
    else:
        print("No solution found")

```
    
