# Q1. 
     
    def func(x, y):
        return x**2 + y**2 + 3*x - 4*y
    
    # Finding the minimum and maximum in a range:
    x_values = (-10, 11)
    y_values = (-10, 11)
    
    min_val = float('inf')
    max_val = float('-inf')
    
    min_point = (0, 0)
    max_point = (0, 0)
    
    for x in x_values:
        for y in y_values:
        
            value = func(x, y)
    
            if value > max_val:
                max_val = value
                max_point = (x, y)
    
            if value < min_val:
                min_val = value
                min_point = (x, y)
    
    print("Minimum value:", min_val, "at point:", min_point)
    print("Maximum value:", max_val, "at point", max_point)



# Q2. 

    import numpy as np
    
    def inverse_matrix(matrix):
        n = len(matrix)
        imatrix = np.eye(n)
        augmented_matrix = np.hstack((matrix, imatrix))
    
        for i in range(n):
            augmented_matrix[i] /= augmented_matrix[i][i]
            for j in range(n):
                if i != j:
                    factor = augmented_matrix[j][i]
                    augmented_matrix[j] -= (factor*augmented_matrix[i])
    
        inverse = augmented_matrix[:, n:] 
        return inverse
    
    # Example usage:
    A = np.array([[2, 1], [5, 3]], dtype = float)
    inverse_A = inverse_matrix(A)
    print("Inverse of A:\n", inverse_A)

# Q3. 



    
