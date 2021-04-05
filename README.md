High Level Approach:
We started by trying to get the login to work with hard coded messages. Once we figured this out, we then abstracted and made
the class structure so we had functions that were reusable across the program. Once we had these functions and classes, we just 
had to think about the logic of the crawler and then use our pre existing functions to implement its functionality.

Challenges:
The first challenge we faced was the login process. It was difficult to construct the correct message and then get the csrf verification.
It took us a while to figure out that the csrf token had to be in the headers and also the data. Once we figured this out we encountered
some issues when receiving responses where the server would hang if we made a recv call and there was no data left. We fixed this by 
looking for the end of a response by either the html end tag using html.parser or a double CRLF (\r\n\r\n). Some minor challenges we faced
were visiting the logout page and pages we weren't supposed to visit but these were easy fixes.

Testing:
We tested the code during the development process by having debug print statements and using the debugger. Once it was finished we simply
ran the crawler multiple times and made sure we got all 5 flags and no errors.