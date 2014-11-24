# HTML rules of thumb

###Take care of using tags unsupported by older browsers

For example, be aware that the `vw`, `vh`, `vmin`, `vmax`, are as of late-2014, unsupported by around 20% of browsers. If in doubt, check [Can I use](http://caniuse.com/).

###On the whole, use *em* not *px*

There is some debate about this, but the weight of opinion is that pixels do not really have much place in modern web design. See, for example [Taking the “Erm..” Out of Ems](http://webdesign.tutsplus.com/articles/taking-the-erm-out-of-ems--webdesign-12321).

###Don't nest your divs more than necessary

If you are using Bootstrap, for example, you are likely to have a layout that looks something like this:

    <div class="container">
      <div class="row">
        <div class="col-md-12">
    	  Hello world
        </div>
      </div>
    </div>

Try to avoid adding any additional *divs* between the *container*, the *row* and the *col*. If you want to add behaviour, then add an additional class within an appropriateexisting *div*.

[in progress]
