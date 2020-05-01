<h1>I have included examples of code that I worked on over the course of a two-week sprint, in which an task from a client was simulated.
</h1>

We were to make numerous changes to a theatre company's website per their exact specifications. My own work was entirely front-end,
and in that time, I completed three key tasks.


<h2>The First Task</h2>

The first task saw me make several changes to the login page, including adjusting the input fields for the email and password,
which was accomplish through a handful of simple classes on the CSS page:

```/*This class was added to move most of the content of the login page to the left*/ 
.loginpadding {
    padding-left: 50px;
}

/*This class was also added to move certain elements on the login page left*/
.loginhtwo{
    padding-left: 65px;
    padding-top: 50px;
}
######/*This class was added to move the login button more to the right*/
.loginhthree{
    padding-right: 45px;
    padding-left: 5px;
}
```


They were in turn implemented on the login page itself, along with bootstrap grids to accomodate a variety of screen sizes and adjustements to the login button's size and the content margins:

```<h2 class="loginhtwo">@ViewBag.Title.</h2> 
<div class="row">
    <div class="col-md-8">
        <section class="loginpadding" id="loginForm">
            @using (Html.BeginForm("Login", "Account", new { ReturnUrl = ViewBag.ReturnUrl }, FormMethod.Post, new { @class = "form-horizontal", role = "form" }))
            {
                @Html.AntiForgeryToken()
                <h4 class="col-md-8 col-sm-8">Use a local account to log in.</h4>
                <hr />
                @Html.ValidationSummary(true, "", new { @class = "text-danger" })
                <div class="form-group">
                    @Html.LabelFor(m => m.Email, new { @class = "col-md-2 control-label" })
                    <div class="col-xs-8 col-sm-7 col-md-5 col-lg-5 col-xl-4"> @*I changed the length of the input fields to account for additional sizes, which I also added*@
                        @Html.TextBoxFor(m => m.Email, new { @class = "form-control" })
                        @Html.ValidationMessageFor(m => m.Email, "", new { @class = "text-danger" })
                    </div>
                </div>
                <div class="form-group">
                    @Html.LabelFor(m => m.Password, new { @class = "col-md-2 control-label" })
                    <div class="col-xs-8 col-sm-7 col-md-5 col-lg-5 col-xl-4"> @*I changed the length of the input fields to account for additional sizes, which I also added*@
                        @Html.PasswordFor(m => m.Password, new { @class = "form-control" })
                        @Html.ValidationMessageFor(m => m.Password, "", new { @class = "text-danger" })
                    </div>
                </div>
                <div class="form-group">
                    <div class="col-md-offset-2 col-md-10">
                        <div class="checkbox">
                            @Html.CheckBoxFor(m => m.RememberMe)
                            @Html.LabelFor(m => m.RememberMe)
                        </div>
                    </div>
                </div>
                <div class="form-group">
                    @*<div class="col-md-offset-2 col-md-10"> 
                        <input type="submit" value="Log in" class="btn btn-default" />
                    </div>*@
                    <div class="iconBtnContainer">
                        <div class="loginhthree">
                         <button class="iconBtn" type="submit">Login @*I removed the onclick event handler*@
                         </button>
                         </div>
                    </div>
                </div>
                <p class="col-md-8">
                    @Html.ActionLink("Register as a new user", "Register")
                </p>
                /* Enable this once you have account confirmation enabled for password reset functionality*/
                    <p class="col-md-8">
                        @Html.ActionLink("Forgot your password?", "ForgotPassword")
                    </p>
            }
        </section>
    </div>
    @*<div class="col-md-4">
        <section id="socialLoginForm">
            @Html.Partial("_ExternalLoginsListPartial", new ExternalLoginListViewModel { ReturnUrl = ViewBag.ReturnUrl })
        </section>
    </div>*@
</div>
```
<h2>The Second Task</h2>

The second task saw me make several style changes to the website's Details page for its photos. However, there were no rigid guidelines provided, and as such I was given a relative degree of freedom to customize the look to my liking. Apart from a few changes to the margins, and keeping within the prescripted color scheme, I incorporated a custom font. It is my conviction that, while risking the legibility of the text, it is imperative that an aesthetic identity be established for a company. This includes being able to invoke, in broad terms, a sensational feeling that harkens back to the organization's key features, in this case, the rousing movements and Dionysian splendor of theatre. 


```
/*This class was added to put spacing between the photo and the text on the Photo Details page*/
.image-spacing{
    margin-top: 10px;
    margin-bottom: 10px;
    border-top: 10px;
    border-bottom: 10px;
    padding-top: 20px;
    padding-bottom: 20px;
    padding-right: 20px;
    padding-left: 20px;
    max-width: 500px;
}
/*This class was added to give visual flair to the text on the Photo Details page*/
.photodetailspagedecorating {
    font-family: 'BioRhyme';
    text-decoration-line: underline;
    text-decoration-style: inherit;
    text-decoration-color: crimson;
    padding-left: 40px;
    padding-right: 40px;
    padding-top: 20px;
}

.backandeditspacing{
    padding-left: 40px;
    padding-bottom: 10px;
}
```


<h2>The Third Task</h2>

In the third and final task, I created a *.class1 .class2* CSS selector in order to resolve a priority conflict between a class and an ID which had prevented me from change the font color of the navigation bar's drop-down menus. 
```
#navbarSupportedContent .color { 
    color: #212529
}
```

It was subsequently applied to the layout page:

```
<!--Events-->
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle color" href="#" id="navbarDropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                        Events
                    </a>
                    
<!--Company-->
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle color" href="#" id="navbarDropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                        Company
                    </a>
                    
<!--Admin-->
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle color" href="" id="navbarDropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                        Admin
                    </a>
                    
<!--Subscriber-->
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle color" href="#" id="navbarDropdownMenuLink" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
                        Subscriber
                    </a>
```                    
                    
The second part of the task was to adjust the speed at which the navigation bar and logo expanded and shrank when scrolling, which was resolved with the following change on the CSS page:
 
``` 
#menu {
            transition: 0.8s;
            padding: 20px;
        }

        #logo {
            transition: 0.8s;
        }
```        
<h2>Final Thoughts<h2>

Though my work was chiefly in the realm of front-end development, utilizing HTML and CSS, I aim to utilize these skills to better develop the user experience of a client's means of interfacing with their customers, including through websites. By balancing UI legibility with aesthetic presentation, a company can more easily create a distinct identity within the minds of its userbase, especially in an age that champions minimalism: there is a real opportunity to stand out while remaining approachable. 
