<p align="center"><img src="/assets/v1.png" /></p>

<h1 align="center">AI wizards, time to shine!</h1>
<h2 align="center"> 
  <p>Nimble & Web Scraping Club's epic 72-hour AI challenge begins on June 27, 2023.</p>
  <p>The top 10 winners bag a sweet $1000 credit for the Nimble system. And the champion?</p>
  <p>That's a cool $1000 Nimble credit PLUS $500 cash</p>
  <p>Mark the date, prep your code and aim for glory.</p>
</h2>
<!-- Display the countdown timer in an element -->
<p id="demo"></p>

<script>
// Set the date we're counting down to
var countDownDate = new Date("Jan 5, 2024 15:37:25").getTime();

// Update the count down every 1 second
var x = setInterval(function() {

  // Get today's date and time
  var now = new Date().getTime();

  // Find the distance between now and the count down date
  var distance = countDownDate - now;

  // Time calculations for days, hours, minutes and seconds
  var days = Math.floor(distance / (1000 * 60 * 60 * 24));
  var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  var seconds = Math.floor((distance % (1000 * 60)) / 1000);

  // Display the result in the element with id="demo"
  document.getElementById("demo").innerHTML = days + "d " + hours + "h "
  + minutes + "m " + seconds + "s ";

  // If the count down is finished, write some text
  if (distance < 0) {
    clearInterval(x);
    document.getElementById("demo").innerHTML = "EXPIRED";
  }
}, 1000);
</script>
