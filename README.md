# RestaurantManagementSystem
Subject Project
### Debugging and error Handling in Asp.net core 6
- debugging the server side
- debugging the client side
- handle errors effectively
- damage that errors can do
#### This Rise of ASP
Active Server Pages began entirely as a procedural bases web-bases script that is to say when there a request to the page<br>
it began executing the script at the top and finished when it reached the bottom. Error handling was simply non-existent<br>
with simply on error resume next statement, which did exactly what it sounds like, keep rolling farward if you enconter an<br>
error. There was also no interactive debugger to figure out problems, you simply wrote out the details you needed to look at<br>
with the response.Write statement.<br>
<b>this programatic chaos could not hold. Very quickly, ASP programmers adopted a structure whereby we examine the details of the request
comming-in in a multi-switch statements, actually a Select Case statement which was equivalent of the switch statement in VBScript. The 
language of active server pages</b><br>
By placing code within different case statements we were able to achieve crude form of encapsulation and isolation and make some sense of our code<br>
The pattern become universal, even all these years later for a totally dead web technology you can still get google results with the term select <br>
Case ASP classic.

