// Show dropdowns on hover. A short delay is used to prevent the dropdown being triggered if the
// mouse is simply positioned over a dropdown link when the page loads.
$(document).on('mouseenter', '[data-toggle="dropdown-hover"]', function(e) {
  var timer
  var $el = $(this)
  var $dropdown = $el.find('.dropdown-menu')

  clearTimeout(timer)
  timer = setTimeout(function() {
    $el.addClass('show')
  }, 300)

  $dropdown.on('mouseenter', function(e) {
    clearTimeout(timer)
  })

  $el.on('mouseleave', function(e) {
    clearTimeout(timer)
    timer = setTimeout(function() {
      $el.off('mouseleave')
      $dropdown.off('mouseenter')
      $el.removeClass('show')
    }, 300)
  })
})

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>title</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
  </head>
  <body>
    <!-- page content -->
  </body>
</html>

# Ruby Greeter class
class Greeter
   def initialize(name)
      @name = name.capitalize
   end
   def sayHello
      puts "Hello #{@name}!"
   end
end

hello = Greeter.new("World")
hello.sayHello
