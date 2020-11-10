---
layout: post
title: The Creation of A Postifix Calculator
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/thumb.png
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
Writing the code for the calculator was not as hard a task as it initially  
seemed. In the beginning, I had strong psuedocode because i knew what i  
needed to do but i didnt know what exactly to write in terms of python.  
I dedcided to split up the code into two sections, an operations function  
and then an evaluate function. This was because i already knew what i needed  
to do for the operations function. All i needed to do was pass in the numbers  
and operation and then just perform it. The difficulty came with the evaluate  
function. In the start, I had all the code i needed and i knew that i was some  
what right but I kept getting zero as an output regardless. Here is where talking  
to Mr. Lee helped me out a lot. Without saying too much, he helped me going in the  
right direction and my code began to work, though it was not fully functional yet.  
I had one silly mistake where i used the numbers in the wrong order for the  
operations. Once again, Mr. Lee came in clutch and had me write out a line from the  
csv and i found that mistake very quickly. Overall, the process was not too  
difficult because having a lot of outside sources to bounce ideas off of was  
so helpful in itself.