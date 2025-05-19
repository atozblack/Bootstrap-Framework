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
