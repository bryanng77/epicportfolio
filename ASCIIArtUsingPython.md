[Back to Home](README.md)

# ASCII ART (using Python)

I came across this form of art called **ASCII** art, and I read somewhere on the internet that we could "replicate" the effects of this art using Python **(screams!!)**. Of course, this really intriguied me I decided to find out how I can do it in the simplest way possible (without any fancy code :-P)

For those are not familiar with what **ASCII art** is, it **ASCII art** is a graphic design technique that uses computers for presentation and consists of pictures pieced together from individual characters. It looks a little something like this:

![image](https://user-images.githubusercontent.com/79688274/128904113-6ade1ad2-92c7-4e81-a4fe-550090cc806d.png)


Here's an image of Dwight Schrute from the sitcom, "The Office". 

But of course, I won't be doing something so complex today because i'm not skilled enough. Therefore, I have decided to transform _my name_ into an piece of ASCII art.

### There are two ways that we can do this:

#### First method:


```python
# Let's use the print function for every single line that we have and carefully insert the characters.

print("BBBBB    RRRRR    YY  YY    AA      NN      N")
print("B   B    R   R     YYY     A  A     N N     N")
print("B  B     RRRR       Y     AAAAAA    N  N    N")
print("BBB      RR         Y    A      A   N   N   N")
print("B  B     R R        Y    A      A   N    N  N")
print("B   B    R  R       Y    A      A   N     N N")
print("BBBBB    R   R      Y    A      A   N      NN")

# This can't be compared to the Dwight picture, but maybe one day I'll be able to acheive that level of skill HAHAHA
```

    BBBBB    RRRRR    YY  YY    AA      NN      N
    B   B    R   R     YYY     A  A     N N     N
    B  B     RRRR       Y     AAAAAA    N  N    N
    BBB      RR         Y    A      A   N   N   N
    B  B     R R        Y    A      A   N    N  N
    B   B    R  R       Y    A      A   N     N N
    BBBBB    R   R      Y    A      A   N      NN


#### Second Method:
For the second method, we can use a multi-line string instead, and store the string in a variable using triple quote-marks:


```python
name = """
BBBBB    RRRRR    YY  YY    AA      NN      N
B   B    R   R     YYY     A  A     N N     N
B  B     RRRR       Y     AAAAAA    N  N    N
BBB      RR         Y    A      A   N   N   N
B  B     R R        Y    A      A   N    N  N
B   B    R  R       Y    A      A   N     N N
BBBBB    R   R      Y    A      A   N      NN  
"""

# We will now print our "name" variable and TADAAA, we will still get the same results!
print(name)
```

    
    BBBBB    RRRRR    YY  YY    AA      NN      N
    B   B    R   R     YYY     A  A     N N     N
    B  B     RRRR       Y     AAAAAA    N  N    N
    BBB      RR         Y    A      A   N   N   N
    B  B     R R        Y    A      A   N    N  N
    B   B    R  R       Y    A      A   N     N N
    BBBBB    R   R      Y    A      A   N      NN  
    


## Conclusion:
Well, I really had lots of fun doing this even though it was such a lame thing to do HAHAHA! Feel free to try it out on your own using your own name or other words! If you're feeling more adventurous, maybe you can try creating a **SNOWMAN** using either of the methods. 


```python
# Making a Snowman using the First Method:

print("      *     *                    ")
print("                      *          ")
print("*         *  HHH            *    ")
print("     *      HHHHH *     *        ")
print("           HHHHHHH        *      ")
print(" *         HHHHHHH               ")
print("     *   HHHHHHHHHHH    *     *  ")
print("         *   @ @   *             ")
print("        *     ^     *            ")
print("  *       *       *         *    ")
print("         SSS * * S               ")
print("         * SSSSSSSS *            ")
print("       *      O   SS  *          ")
print("      *       O    S   *         ")
print("      *       O        *         ")
print("       *              *          ")
print("           *   *   *             ")
```

          *     *                    
                          *          
    *         *  HHH            *    
         *      HHHHH *     *        
               HHHHHHH        *      
     *         HHHHHHH               
         *   HHHHHHHHHHH    *     *  
             *   @ @   *             
            *     ^     *            
      *       *       *         *    
             SSS * * S               
             * SSSSSSSS *            
           *      O   SS  *          
          *       O    S   *         
          *       O        *         
           *              *          
               *   *   *             

Alright, enough of me talking. Have fun and happy coding!
