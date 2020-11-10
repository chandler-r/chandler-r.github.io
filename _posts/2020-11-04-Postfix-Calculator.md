---
layout: post
title: The Creation of A Postifix Calculator
cover-img:
thumbnail-img:
subtitle: by Chandler Reyes
---

# My Take on A Postfix Calcultor

## The Total Average of The Dataset
The ending average of the dataset wound up being 529.91.  
I did this by making two different variables, one where I would  
add 1 for everyone and then another where I just keep adding the  
number that evaluate(row) produces. This would give me the total  
sum of all the results and I just divided it by the number of rows.

## The Use of Stacks in the Postfix Calculator
The calculator depends heavily on stacks to work. In the postfix  
calculator, the stack is used to hold all the results of each  
operation that is done. While the code is looping through each row  
of operations, the numbers are being pushed into the stack. Once the  
operation is found in the row, the top two numbers are popped, that  
operation is performed, then the result is pushed back in. This  
happens for however many rows there are. These lines of code show  
exactly what the process is when the loop is running:
```javascript
for i in range(len(row)):
        /*
        if the object at index i is in the operation list
        pop the top two numbers from the stack output
        then perform an operation when the first number is the second one popped 
        and the second one is the first one popped, then push the result back in
        */
        if row[i] in ["*", "-", "+"]:
            numA = output.pop()
            numB = output.pop()
            C = operation(row[i] , int(numB) , int(numA))
            output.push(C)
        else:
            //if no operation is present just push the numbers to the stack
            output.push(row[i])
```

## The Process of Creating the Code for the Calculator
