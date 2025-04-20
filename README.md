



     
    def func(x, y):
        return x**2 + y**2 + 3*x - 4*y
    
    ## Finding the minimum and maximum in a range:
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
