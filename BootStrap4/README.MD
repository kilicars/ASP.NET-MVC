Current ASP.NET MVC framework uses some CSS features that are not included in BootStrap4 anymore. If you create a new ASP.NET MVC application 
and update the packages through Nuget Package Manager then you will get the last version of BootStrap and as a result you will see
that the navigation bar is broken as seen below ![image of the navigation bar after update](https://github.com/kilicars/ASP.NET-MVC/blob/master/BootStrap4/after.png)

If you change the code for the navigation bar in _Layout.cshtml to the below one then the issue is resolved

    <nav class="navbar navbar-expand-sm navbar-dark fixed-top bg-dark">
        <div class="container">
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation"></button>
            @Html.ActionLink("MVC Bank", "Index", "Home", new { area = "" }, new { @class = "navbar-brand" })
            <div class="navbar-collapse collapse" id="navbarSupportedContent">

                <ul class="nav navbar-nav mr-auto">
                    <li class="nav-item">@Html.ActionLink("Home", "Index", "Home", null, new { @class = "nav-link" })</li>
                    <li class="nav-item">@Html.ActionLink("About", "About", "Home", null, new { @class = "nav-link" })</li>
                    <li class="nav-item">@Html.ActionLink("Contact", "Contact", "Home", null, new { @class = "nav-link" })</li>
                </ul>
            </div>
        </div>
    </nav>
    
Now the navigation bar is as it is supposed to be : 
![image of the navigation bar after fix](https://github.com/kilicars/ASP.NET-MVC/blob/master/BootStrap4/before.png)

You can check the full code from _Layout.cshtml.
