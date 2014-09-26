# Using .append() in jQuery

Assume we have a set of news headlines which we store in a variable:

    var results = {
        { 
            url: "http://collective-news/123",
            headline: "Police called in over killer goldfish" 
        },
        { 
            url: "http://collective-news/123",
            headline: "Street light left on all day"
        },
        { 
            url: "http://collective-news/123",
            headline: "Father dialed 999 because it was raining"
        }
    }

We can use `append` like this:

    $.each(results, function(i, result) {
      $( '#news' ).append('<a href="' + result.url + '">' + result.headline + '</a>');        
    });

`each` is a jQuery function. [Look it up](http://api.jquery.com/jquery.each/).
 
We can also do this:

    $.each(results, function(i, result) {
      $( '#news' ).append( $('<a>', {
        href: result.url,
        text: result.headline
      }));

Or we can use `appendTo`, which is perhaps a bit easier on the eye.

    $.each(results, function(i, result) {
      $('<a>', {
        href: result.url,
        text: result.headline
      }).appendTo('#news');
    });

Even better would be:

    var links = '';
    $.each(results, function(i, result) {
      links += $('<a>', {
        href: result.url,
        text: result.headline
      });
    });
    $( '#news' ).append(links);

Why would this be better? Because DOM insertion is expensive. Inserting all your results once, instead of each one separately, will be much quicker. How much quicker? If anyone is up for it, it would be a very interesting exercise to try it both ways on a single page and use the DevTools to get an estimate of the difference.