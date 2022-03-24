### Section A

Considering the fact that I am writing to a student:

Hi there, I am Elian and I am here to review your task submission as well as help you to move forward and clarify any
doubt or problem that you might have.

Firstly I would like to thank you for you effort and the time you took to complete the task. Good news! I like the way
you thought how to solve it and you are very close to perfect.

I am aware that you got some errors during execution but no problem, I am here to help you and give you some extra
advices as well as best practices that are good to follow.

### Style

I would begin talking about the code style. The first thing that caught my attention was line 2. In every programming
language there is a term, called **_“indentation”_** that refers to the spaces before a code line.

Without indentation the code becomes very hard to parse. Indentation is the key to manageability and maintainability. and
it can quickly becomes very hard to fix problems and scale the code in the future if not used correctly.

Where in other programming languages the indentation in code is for readability only, the indentation in Python is very
important as it is used to indicate a block of code.

So the line 2 does not have the correct number of spaces to indicate a block an therefore will lead to indentation
error. I am considering it as a style problem, but in fact it Python it is very important and prevents the correct
execution and I am considering it as a style problem just because it is treated like so in the major part of other
programming languages. Just keep in ming to use it everywhere. Good programmers always follow this rule, despite the
language. I would invite you to read more about indentation and the importance in Python by following this link:
https://peps.python.org/pep-0008/

### Correctness

One of the key problems why you see errors during execution was the indentation, mentioned before.

There is just one another problem with your code. If you see carefully to line 5, you are inside a loop initialized in
line 4. I am glad that you used a function that Python provides by default, the _**sort**_ function but that function
accepts as a parameter a string and then orders the letters of that string in alphabetical order. You can simply realize
that you called the sorted function without passing anything and therefore it does not execute correctly. You were very
close. Since you are iterating each string of the **_strs_** array saving the value in variable _**i**_, then i was the
right variable to be placed inside the parenthesis or in other words, as a parameter passed to sorted function. After
doing this change, as well as the indentation I am sure that your code will execute correctly and you will be able to
see the correct result as you expected!

### Efficiency

Talking about efficiency, I would say well done!
Maybe you have thought at the beginning that looking at each letter in a word might be a start for the solution but
going through each letter and figuring out if 2 words have the same letters might take too long. Deciding to sort each
letters of a certain string in alphabetical order would give us the possibility to have identical strings and therefore
be sure to decide if those strings where derived from two or more strings inside an anagram group. So, in simple works,
good job for the idea!

### Documentation

Documentation is one of the key principles you have to keep in mind while coding. It helps anytime and everybody. Every
programming language provides the possibility to write comments that can be included inside the source code. They are
added with the purpose of making code easier for humans to understand and are generally ignored by compilers and
interpreters. So what it means is that you can write explanations about your code everytime you think it is needed. You
can write them in human language and the purpose it to help you and probably your colleagues if they will came across
your code.

Another thing to consider very carefully is the name of variables. Variables should be self-explanatory for what they
held inside. Try to avoid using ~~i~~, ~~x~~, ~~strs~~, ~~result~~. Instead use _**word**_, _**sordedWord**_, _**words**_, _**
anagrams**_ etc.

Below I am providing the correct solution, including even best practices and suggestions. Good job and keep practicing!

Solution:

```
class Anagrams:
   def groupAnagrams(self, words):
      anagrams = {}
      
      for word in words:  
         #sort the letters of the word in alphabetical order
         sortedWord = "".join(sorted(word))
         '''
         If the sorted word already exists as a key in results object then append the word (not sorted) to its list. 
         Otherwise add a new key => value pair with sorted word as key and a list continaing original word.
         '''
         if sortedWord in anagrams:
            anagrams[sortedWord].append(word)
         else:
            anagrams[sortedWord] = [word]
            
        #returns the list of all grouped anagram lists    
      return list(anagrams.values())
      
#initialize object      
anagramObj = Anagrams()

#print the grouped anagrams by array
print(anagramObj.groupAnagrams(["eat", "tea", "tan", "ate", "nat", "bat"]))