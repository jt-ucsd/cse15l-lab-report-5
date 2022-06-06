# Lab Report 5

By: jt

I found the tests with different results by creating a java file.  The file would loop for each .md file in the folder and run my markdown parser on it and the one provided in lab 9.  Then, it would print out the links along with the file name.  I could then scroll through the output and manually compare.

Links to Tests that Fail:

1) Link to [488.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/488.md)

2) Link to [579.md](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/579.md)

## 488.md

1) For this file, my implementation is correct.

2) The correct answer is that there is one link ``</my uri>`` and we should expect ``[</my uri>]``.

![488.md File Output](https://raw.githubusercontent.com/jt-ucsd/cse15l-lab-report-5/main/Lab%20Report%205%20-%20488.md%20File%20Output.jpg)

3) The bug in the program is that if there is a space anywhere in the potential link, it will be ignored.  As a result, since there is a space in between ``</my uri>``, the program doesn't count it as a link to add to its ArrayList.  To fix this, you can just remove the part that checks for spaces as we are checking if markdown considers it a link, not whether the link is valid or not.

![488.md Fix](https://raw.githubusercontent.com/jt-ucsd/cse15l-lab-report-5/main/Lab%20Report%205%20-%20488.md%20File%20Fix.jpg)

## 579.md

1) For this file, my implementation is correct.

2) The correct answer is there is no links and we should expect ``[]``.

![579.md File Output](https://raw.githubusercontent.com/jt-ucsd/cse15l-lab-report-5/main/Lab%20Report%205%20-%20579.md%20File%20Output.jpg)

3) The bug in the program is there is no where that checks if the link is for a link or an image.  We can simply fix this by adding an if condition immediately after finding the open bracket and checking if the character before it is an exclamation point or not.

![579.md Fix](https://raw.githubusercontent.com/jt-ucsd/cse15l-lab-report-5/main/Lab%20Report%205%20-%20579.md%20File%20Fix.jpg)
