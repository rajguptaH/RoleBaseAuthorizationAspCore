# Role Based Authorization in asp dot net core Mvc
- You Have To Tell In The Startup You Are going to use authentication write below code in start.cs and this says you are adding the authentication service in your application using a cookies
```c#
builder.Services.AddAuthentication(CookieAuthenticationDefaults.AuthenticationScheme).AddCookie();
```
- after that you have to tell the application to add authentication and authorization
```c#
app.UseAuthentication();
app.UseAuthorization();
```
- After that you have to create a simple AccountController With Login Get Post Methods and Logout Method With Simple View Then You Have To Add a attribute Called [AllowAnonymous] This will keep this method accessable for anyone without login see below 
```c#
[AllowAnonymous]
[HttpGet]
public IActionResult Login()
{
    return View();
}
```
- And Put a [Authorize] attribute where you want only authorization person can use this method
```c#
[Authorize]
public IActionResult Index()
{
   return View();
}
```
