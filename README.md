This is an updated version of the example code for the popular RailsCast (Pro)
episode, "Nested Model Form (revised)", which was made for Rails 3.
This example is based on a fresh install of Rails 4 with the relevent code migrated
from the original RailsCast example.

I originally attempted to get the original Rails 3 example working, but ran into
various issues. I decided to reimplement the example for Rails 4 instead of
further troubleshooting the original.

http://railscasts.com/episodes/196-nested-model-form-revised


The episode is available to RailsCasts Pro subscribers (as a Rails developer
you're probably already a member - if not, you're missing out). The example
code is public on GitHub: https://github.com/railscasts/196-nested-model-form-revised



## Some key changes for the Rails 4 example:

1. Rails 4 uses Strong Parameters in the controller instead of attr_accessible in
the models. I added a survey_params private method to the surveys controller, which
permits the necessary nested parameters. It took some googling and trial and error
to get right, so hopefully this helps save others some time.
2. Turbolinks was causing the various AJAX links like "Add Answer" and "remove" to
not work consistently. This is due to the fact that with Turbolinks, the DOM's ready
event isn't ever fired except on the very first page load. Therefore the attempt to
add event listeners fails because those elements aren't on the page at the time.
You can learn more on this RailsCast: http://railscasts.com/episodes/390-turbolinks
In any case, the solution is to add a few lines to the .coffee file to ensure the
DOM's ready event fires on every page. Alternately you can use the jQuery Turbolinks
gem: https://github.com/kossnocorp/jquery.turbolinks which I tested as well and
should do the job if you prefer that route.
