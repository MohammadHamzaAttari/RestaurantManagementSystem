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
> Old Code Example
```
Dim requestVaue
Select Case Request.Form("submit")
Case ""
    initial Get request
    Response.Write("html")
    'write out the rest of initial page
Case "Create initial order"

     Dim productName=Request.Form("txtproduct")
     'process the form submission
end Select     

```
Microsoft implemented it in the backend so that it could become invisible a good thing. In their 1.0 version ASP.Net, the new platform adoption of active
server pages, code was event driven with literal event handlers for submit buttons and other controls you would put on the page by moving from VBscript
to Visual Basic .Net or C#.

The technology open the door for complete and formal implementation of errors handling as well as bringing about an interactive debugger, a huge step 
forward.
![Screenshot from 2022-12-26 15-44-41](https://user-images.githubusercontent.com/66419330/209540094-b2ce07f8-ae97-40f2-9422-a38f0a510a8a.png)
Further more! this created the first separation between the HTMl user interface and back-end code.
<b>It was not perfact</b>
But compared to what we worked with before, it was wonderful.
#### Cracks in Metaphor
The problem was that the Microsoft had adopted a metaphor that did not 100% apply web-oriented communications.
In traditional desktop development, you have got a message loop running in the background and to derive programming events, you create event hooks, which
interrupt that loop and give you an upportunity to respond to events. Button click, text entry, selection from a dropdown This is all common sense for a 
developer that is the model that web forms adopted. It is right there in the name, Web Forms as in form-based development like on your desktop.
<b>Web Communication is Different</b>
- it is request based
- Your desktop application is sitting there running in memory and those event hooks are simple and small interruptions.
To model this on the web, you have to essentially ship the entirely of your application back and forth between the user and the server, atleast the client
side of it.
> this approach had problems with persistence between requests, problem with navigation back and forth and above all
> it continued to strongly intermingle the presentation logic with the bussiness logic making the system nearly impossible to unit test.
To fix these and other problems, Microsoft deprecated web forms and instead focused on an Architectural Model called MVC, which would split the
presentation code, the bussiness layes and the routing logic into separate pieces. This was three steps farward and one step back.While it solved the 
problems of intermingle logic and create a much more request-centric model of development, it broke a practical link in ordering together of the 
presentation logic and routing that was going to exist for every developer in every project
In short, it over-separated things, leading to some challenges in debugging, which leads us to the thus far final step in evolution for ASP.Net.
#### The ultimate Evolution (so far)
- Razor Pages or MVVM
MVVM stands for Model-View-ViewModel and coordinates these elements together. Razor Pages restore the best elements of a reactive model of web form with 
the clean and total separation of logic of MVC.
