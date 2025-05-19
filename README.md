# Bootstrap-Framework
Learn About Bootstrap Framework Part 1

We can learn about Bootstrap in here. From basic until how to create simple Landing page site.

Index :

1. 2 Column
2. 3 Column
3. typography
4. tables
5. images
6. pageheader
7. alerts
8. button
9. progressbar
10. collapselist

In Typography.html

This Code : 

<!--Highlight-->
		<p>With Bootstrap we can <mark>highlight</mark> text.</p>
		
		<!--Dotted Underline-->
		<p>We can also <abbr title="Explanation">Underline</abbr> text with a dotted line.</p>
		<hr />
		
		<!--Blockquotes-->
		<div class="col-lg-12 bg1">
		<h1>Blockquotes</h1>

		<blockquote>
			
			<p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.</p>
			
			<footer>Lorem Ipsum Source</footer>
		
		</blockquote>
		<hr />
		</div>
		<!--Blockquotes  element represents content that is quoted from another source, optionally with a citation which must be within a footer or cite element, and optionally with in-line changes such as annotations and abbreviations-->

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------

  In Image.html

  This Code :

  <body>

<div class="container-fluid">
        	<h1>Photo Gallery</h1>

		<blockquote>
  <table class="table table-striped">
	<thead class="bg1">
      <tr>
        <th>Firstname</th>
        <th>Lastname</th>
        <th>Grade</th>
        <th>Photo</th>
      </tr>
    </thead>

    <tbody>
      <tr class="danger">
        <td >John</td>
        <td >smith</td>
        <td >80</td>
        <td> <img class="img-responsive" src="03.jpg" width="500" height="300"> </td>
      </tr>
      <tr class="info">
        <td >Ted</td>
        <td >Crow</td>
        <td >90</td>
         <td> <img class="img-responsive" src="02.jpg" width="500" height="300"> </td>
      </tr>
      <tr class="success">
        <td >Molly</td>
        <td >Doe</td>
        <td >93</td>
         <td> <img class="img-responsive" src="01.jpg" width="500" height="300"> </td>
      </tr>
    </tbody>
	
  </table>
  	<footer>Molly Grade Highest</footer>
		
		</blockquote>
		<hr />
</div>

<!--In this code i combine Table, Blockquote and image-->

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------

In Progressbar.html

This Code : 

 /* Preloader Styling */
    #preloader {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: #ffffff;
      z-index: 9999;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
    }

    #preloader .progress {
      width: 60%; /* progress bar container */
      margin-top: 20px;
      height: 25px; /* progress bar height*/
    }

    #preloader .progress-bar {
      /* progress bar text percentage */
      color: #111111; /* color of  */
      font-weight: bold;
      line-height: 25px; /* height progress bar */
      font-size: 14px;
    }

    <script>
$(document).ready(function() {
    let $progressBar = $('#preloader .progress-bar');
    let $percentageText = $('#preloader .percentage-text');
    let currentProgress = 0;
    let animationTime = 1500; // Total duration of the progress bar animation in milliseconds (e.g., 1.5 seconds)
    let updateInterval = 20;  // How often the progress is updated (milliseconds)
    
    // Calculate how much to increment per interval to reach 100% within animationTime
    let increment = 100 / (animationTime / updateInterval);
    let progressInterval;

    function updateProgressBar() {
        currentProgress += increment;
        if (currentProgress > 100) {
            currentProgress = 100;
        }
        
        $progressBar.css('width', currentProgress + '%').attr('aria-valuenow', currentProgress);
        $percentageText.text(Math.round(currentProgress) + '%');

        if (currentProgress >= 100) {
            clearInterval(progressInterval);
            // Wait for the window.load event to hide the preloader
        }
    }

    // Start the progress bar animation immediately
    progressInterval = setInterval(updateProgressBar, updateInterval);

    $(window).on('load', function() {
        // Ensure the interval is cleared if it hasn't been already
        clearInterval(progressInterval);
        
        // Ensure the progress bar shows 100%
        currentProgress = 100;
        $progressBar.css('width', '100%').attr('aria-valuenow', 100);
        $percentageText.text('100%');

        // Give a slight delay after the progress bar reaches 100% before fading out
        setTimeout(function() {
          $('#preloader').fadeOut('slow', function() {
            // After the preloader disappears, restore scrollability to the body
            $('body').css('overflow', 'auto');
            // Optional: Remove the preloader from the DOM
            // $(this).remove(); 
          });
          $('#main-content').fadeIn('slow');
        }, 400); // 400 millisecond delay
    });
});
</script>

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------

  In Collapselist.html

This Code : 

 <div class="panel-group">
      <div class="panel panel-primary">
        <div class="panel-heading">
          <h4 class="panel-title">
            <a data-toggle="collapse" href="#expand1">Collapse Panel Halaman 1</a>
          </h4>
        </div>
        <div id="expand1" class="panel-collapse collapse">
          <ul class="list-group">
            <li class="list-group-item">Item 1</li>
            <li class="list-group-item">Item 2</li>
            <li class="list-group-item">Item 3</li>
          </ul>
          <div class="panel-footer">Footer Panel 1</div>
        </div>
      </div>
    </div>
  </div>

  <div id="page2" class="page-content">
    <h2>Konten Halaman 2</h2>
    <div class="panel-group">
      <div class="panel panel-primary">
        <div class="panel-heading">
          <h4 class="panel-title">
            <a data-toggle="collapse" href="#expand2">Collapsible panel Halaman 2</a>
          </h4>
        </div>
        <div id="expand2" class="panel-collapse collapse">
          <div class="panel-body">Panel Body Halaman 2</div>
          <div class="panel-footer">Panel Footer Halaman 2</div>
        </div>
      </div>
    </div>
    <hr>
    <button type="button" class="btn btn-info" data-toggle="collapse" data-target="#ex1">Collapse Konten Halaman 2</button>
    <div id="ex1" class="collapse">
     <div class="row">
        <div class="col-lg-4 bg1">
        <h2> My First Bootstrap Web Page 1 (Hal 2)</h2>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus expedita pariatur, praesentium dolorum suscipit,
          perspiciatis quas et aspernatur earum sunt autem debitis,
          odit deleniti veniam necessitatibus aut corrupti facere iusto?
        </p>
        </div>
        <div class="col-lg-4 bg2">
          <h2> My First Bootstrap Web Page 2 (Hal 2)</h2>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus expedita pariatur, praesentium dolorum suscipit,
          perspiciatis quas et aspernatur earum sunt autem debitis,
          odit deleniti veniam necessitatibus aut corrupti facere iusto?
        </p>
        </div>
          <div class="col-lg-4 bg3">
          <h2> My First Bootstrap Web Page 3 (Hal 2)</h2>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus expedita pariatur, praesentium dolorum suscipit,
          perspiciatis quas et aspernatur earum sunt autem debitis,
          odit deleniti veniam necessitatibus aut corrupti facere iusto?
        </p>
        </div>
      </div>
    </div>
  </div>

  <div id="page3" class="page-content">
    <h2>Konten Halaman 3</h2>
    <hr />
    <a href="#ex2" class="btn btn-info" data-toggle="collapse">Simple collapsible Halaman 3</a>
    <div id="ex2" class="collapse">
      <h1>Photo Gallery (Halaman 3)</h1>
      <blockquote>
        <table class="table table-striped">
        <thead class="bg1">
            <tr>
              <th>Firstname</th>
              <th>Lastname</th>
              <th>Grade</th>
              <th>Photo</th>
            </tr>
          </thead>
          <tbody>
            <tr class="danger">
              <td >John</td>
              <td >smith</td>
              <td >80</td>
              <td> <img class="img-responsive" src="03.jpg" alt="Photo 03" width="150" height="100"> </td> </tr>
            <tr class="info">
              <td >Ted</td>
              <td >Crow</td>
              <td >90</td>
               <td> <img class="img-responsive" src="02.jpg" alt="Photo 02" width="150" height="100"> </td> </tr>
            <tr class="success">
              <td >Molly</td>
              <td >Doe</td>
              <td >93</td>
               <td> <img class="img-responsive" src="01.jpg" alt="Photo 01" width="150" height="100"> </td> </tr>
          </tbody>
        </table>
          <footer>Molly Grade Highest</footer>
      </blockquote>
      <hr />
    </div>
  </div>

  <div class="text-center">
    <ul class="pagination">
      <li class="active"><a href="#" data-page="1">1</a></li>
      <li><a href="#" data-page="2">2</a></li>
      <li><a href="#" data-page="3">3</a></li>
    </ul>
  </div>

</div>
</div>

This HTML document creates a web page with two main features:

A preloader animation that displays while the page content is loading.
Pagination to divide the main content into three navigable pages.
Let's break down the key parts:

1. Preloader Functionality:

HTML Structure (<div id="preloader">):

This div covers the entire screen initially (position: fixed, width: 100%, height: 100%, high z-index).
It contains a "Loading..." message (<h4>) and a Bootstrap progress bar (<div class="progress">).
The progress bar has a <span> with class percentage-text to display the loading percentage.
CSS Styling (#preloader, #preloader .progress, etc.):

Styles the preloader to be centered and to cover the page.
Styles the progress bar and the text within it.
Initially, html and body have overflow: hidden; to prevent scrolling while the preloader is active.
JavaScript Logic (within $(document).ready() and $(window).on('load')):

Progress Bar Animation:
When the document is ready ($(document).ready()), a JavaScript interval (setInterval) starts to animate the progress bar.
currentProgress increases from 0 to 100 over a set animationTime.
The width of the .progress-bar and the text in .percentage-text are updated at each updateInterval.
Hiding Preloader & Showing Content:
The $(window).on('load', function() { ... }); event fires when all page resources (including images) have fully loaded.
Inside this event:
The progress bar is explicitly set to 100%.
After a short delay (setTimeout), the #preloader div fades out (fadeOut('slow')).
The overflow style on the body is set back to auto to allow scrolling.
The main content container (<div id="main-content">) fades in (fadeIn('slow')).
The first page of the paginated content (#page1) is made visible by adding the active class.
2. Pagination Functionality:

Content Division (HTML):

The content previously inside <div id="main-content"> is now divided into three separate div elements:
<div id="page1" class="page-content active">...</div>
<div id="page2" class="page-content">...</div>
<div id="page3" class="page-content">...</div>
Each div represents one page of content.
The page-content class is a common identifier for these page sections.
#page1 has the active class initially, making it visible by default.
Unique IDs for Collapsible Elements: The original code had duplicate id="expand" for multiple collapsible panels. These have been changed to unique IDs (id="expand1" and id="expand2") and their corresponding data-toggle links (href="#expand1", href="#expand2") have been updated to ensure each collapse works independently.
Pagination Controls (HTML):

A Bootstrap pagination component (<ul class="pagination">) is added at the bottom of the content.
HTML

<div class="text-center">
  <ul class="pagination">
    <li class="active"><a href="#" data-page="1">1</a></li>
    <li><a href="#" data-page="2">2</a></li>
    <li><a href="#" data-page="3">3</a></li>
  </ul>
</div>
Each list item (<li>) contains a link (<a>).
The data-page attribute on each link stores the page number it corresponds to.
The first pagination link has the active class.
CSS for Hiding/Showing Pages:

A simple CSS rule controls the visibility of the content pages:
CSS

.page-content {
  display: none; /* All pages are hidden by default */
}
.page-content.active {
  display: block; /* Only the page with the 'active' class is shown */
}
JavaScript Logic for Pagination (within $(document).ready()):

An event listener is attached to the click event of pagination links ($('.pagination li a').on('click', ...)).
When a pagination link is clicked:
e.preventDefault();: Prevents the default browser action for the link (which would be to navigate to "#").
let targetPage = $(this).data('page');: Gets the page number from the data-page attribute of the clicked link.
$('.pagination li').removeClass('active');: Removes the active class from all pagination list items.
$('.page-content').removeClass('active').hide();: Removes the active class from all content page divs and hides them.
$(this).parent().addClass('active');: Adds the active class to the parent <li> of the clicked link, highlighting it.
$('#page' + targetPage).addClass('active').fadeIn('fast');: Finds the content page div with the ID corresponding to targetPage (e.g., #page2), adds the active class to it, and fades it in to make it visible.
