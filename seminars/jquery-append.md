# Using $.append() in jQuery

You can use `append` like this:

    $.each(results, function(i, result) {
      $( '#news' ).append('<a href="' + result.url + '">' + result.headline + '</a>');        
    });
 
Where `results` is some list of objects.

You can also do this:

    $.each(results, function(i, result) {
      $( '#news' ).append($('<a>' {
        href: result.url,
        text: result.headline
      }));

Or you can use `appendTo`, which you may find easier on the eye.

    $.each(results, function(i, result) {
      $('<a>' {
        href: result.url,
        text: result.headline
      }).appendTo('#news');
    });

Even better would be:

    var links = '';
    $.each(results, function(i, result) {
      links += $('<a>' {
        href: result.url,
        text: result.headline
      });
    });
    $( '#news' ).append(links);

Why would this be better? Because DOM insertion is expensive. Inserting all your results once, instead of each one separately, will be much quicker. How much quicker? If anyone is up for it, it would be a very interesting exericise to try it both ways on a single page and use the DevTools to get an estimate of the difference.

WARNING: I have not checked the syntax above. There may be errors. Please let me know if you find any.