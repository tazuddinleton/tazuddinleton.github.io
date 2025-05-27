## What is rate limiting?
Rate limiting is the idea of limiting how much resources can be accessed. Let's say you have the capacity in your app to handle 1000 request per minute, and it may fail if more than 1000 request have been made. So youc an use a rate limiter to deny the excess requests to stabilize your system.


So in essence the purpose of rate limiting is to control how much resource can be accessed at a time.


In this article we'll implement a rate limiter in our .NET Core app to control the API access. 

So Let's being!


## Create the project
Create a project where we will implement the rate limiter, you can do it by following commands:

`bash
dotnet new webapi -n ApiRateLimitingDemo
cd weatherforecast
dotnet run
`
The go to `http://localhost:5050/weatherforecast`, the port might be different in your case.

The above comman creates a .NET 9 web api project based on minimal api pattern. 


We will limit access to this api by adding a rate limiter. In .NET 9


