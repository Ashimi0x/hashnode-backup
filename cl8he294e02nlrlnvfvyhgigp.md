## Create and Reuse a Component in HTML5 like Laravel

In Laravel, You can easily create components for sections like Header and Footer and then extend them into Pages where they are required so it is easier to make universal updates to these sections and not have to repeat them across multiple pages. You can easily create and reuse components in Laravel and even JavaScript Frameworks like React and Angular.

If you enjoy clean codes or support the DRY(Don't Repeat Yourself) software principle. This is for you.

In this article, I will create a Header and Footer Component File and reuse that file across our Website.

### Create Component File

In this step, we will create a new folder for components named layouts and create an HTML file for our components with their name. In my case:

layouts/header.html


```
<!-- Main Header -->
<header class="main-header header-style-one alternate-two">

  <!-- Header Upper -->
  <div class="header-upper">
    <div class="inner-container clearfix">
      <!-- Logo -->
      <div class="logo-box">
        <div class="logo"><a href="index.html" title="#"><img src="assets/images/logo.svg" alt="#" title="#"></a></div>
      </div>
      <div class="nav-outer clearfix">
        <!-- Mobile Navigation Toggler -->
        <div class="mobile-nav-toggler"><span class="icon flaticon-menu-2"></span><span class="txt">Menu</span></div>

        <!-- Main Menu -->
        <nav class="main-menu navbar-expand-md navbar-light">
          <div class="collapse navbar-collapse show clearfix" id="navbarSupportedContent">
            <ul class="navigation clearfix">
              <li class="dropdown">
                <a>Events</a>
                <ul>
                  <li><a href="corporate-events.html">Corporate Events</a></li>
                  <li><a href="social-events.html">Social Events</a></li>
                  <li><a href="wedding-events.html">Wedding Events</a></li>
                  <li><a href="virtual-events.html">Virtual Events</a></li>
                </ul>
              </li>
              <li class="dropdown">
                <a>Hotels</a>
                <ul>
                  <li><a href="hotel-reservation.html">Hotel Reservation</a></li>
                  <li><a href="bed-and-breakfast.html">Bed & Breakfast</a></li>
                </ul>
              </li>
              <li><a href="travel-and-tours.html">Travel & Tours</a></li>
              <li class="dropdown">
                <a>Company</a>
                <ul>
                  <li><a href="about.html">About Sela</a></li>
                  <li><a href="team.html">Team</a></li>
                  <li><a href="brands.html">Brands by Sela</a></li>
                  <li><a href="partners.html">Partners</a></li>
                </ul>
              </li>
              <li class="dropdown">
                <a>Moments</a>
                <ul>
                  <li><a href="photo-gallery.html">Photo Gallery</a></li>
                  <li><a href="video-gallery.html">Video Gallery</a></li>
                </ul>
              </li>
              <li><a href="contact.html">Contact</a></li>
            </ul>
          </div>
        </nav>
      </div>

      <div class="other-links clearfix">
        <div class="info">
          <ul class="clearfix">
            <li><a href="tel:+2347081370925"><span class="icon flaticon-smartphone-2"></span><span class="txt">+234 708 137 0925</span></a></li>
          </ul>
        </div>
        <div class="link-box">
          <a href="#" class="theme-btn btn-style-one"><span class="btn-title">Account</span></a>
        </div>
      </div>

    </div>
  </div>
  <!--End Header Upper-->
</header>
<!-- End Main Header -->
``` 

Now We have our component created, the next step is to import it across pages.

### Reuse Component

In this step, We will go to where we want the component to appear on every page and write the following line of code

```
<!-- Start Import Header -->
    <div>
      <p id="header"></p>
     </div>
<!-- End Import Header -->
``` 
This will not give you any results yet as we are not done.

### Trigger the component
In this final step, We will trigger the component using JavaScript

First, Create a JavaScript file in your Layouts folder and name it Layouts.js and write

```
fetch('layouts/header.html')
.then(res => res.text())
.then(text => {
    let oldelem = document.querySelector("p#header");
    let newelem = document.createElement("div");
    newelem.innerHTML = text;
    oldelem.parentNode.replaceChild(newelem,oldelem);
})
``` 
Proceed to the bottom of the pages where you want to reuse the component before the closing </body> tag and include


```
  <script src="assets/js/layouts.js"></script>
``` 

### How this works

- The layouts.js script fetches the header component and returns the content.
- It then identifies the paragraph with the id of "header" and assigns it to the variable of "oldelem".
- Creates a new Div element and assigns it to the variable of "newelem"
- Proceeds to Include the fetched component as part of "newelem"
- And finally, identifies the parent element(node) for the "oldelem" on the page and replaces it with "newelem".

### Conclusion.
Did this on a simple in-house project I was working on with my CTO at [Haqqman](https://haqqman.agency/) in an attempt to maintain clean code, work effectively and beat time and thought to share. I hope you find this helpful.

Don't forget to share, drop comments, and also subscribe so you don't missout on other helpful content I create based on my experience or generally.

Follow me on Twitter too [@Adebowale_Oba](https://twitter.com/Adebowale_Obaa).