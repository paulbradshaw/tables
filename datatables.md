# Level 2: Using the `DataTables` library to create searchable tables

Once you're happy with [using the `Sortable` library to create sortable tables](https://github.com/paulbradshaw/tables), how about making a sortable *and* **searchable** table?

[DataTables](https://datatables.net/) is a JavaScript library which will add a search box, sortable columns and page indexing to a table. 

Like Sortable, you only need to make sure your webpage has a HTML table, and do 3 things:

* Add a link in your HTML to the jQuery JavaScript library *first*
* Add a link in your HTML to the DataTables library *next*
* Add a link in your HTML to the DataTables style sheet
* Add a `class` or `id` attribute to the <table> tag in your HTML, so it can be targeted
* Add a bit of JavaScript which targets that table and applies a `DataTable` function to it

Below I've outlined each step. You'll also need to make sure your webpage is hosted somewhere that you can edit the HTML to include JavaScript links. GitHub Pages, for example, allows you to host webpages. I've [explained more about that here](https://github.com/paulbradshaw/tables/blob/master/githubpages.md).

## Add the JavaScript library links

Between the `<head>` and `</head>` tags in your webpage HTML you need to add two lines of code which import the JavaScript libraries which will help make your table interactive. The *first* library is **jQuery**; the *second* is **DataTables**:

`<script type="text/javascript" src="https://code.jquery.com/jquery-2.2.4.min.js"></script>`

`<script type="text/javascript" src="//cdn.datatables.net/1.10.12/js/jquery.dataTables.min.js"></script>`

The reason that they need to come in this order is that DataTables is a *plug-in* for the jQuery JavaScript library: it *needs* jQuery first in order to work.

Now that they've been imported, we can use them. But first, a bit of style...

## Add the CSS link

DataTables uses CSS to add a bit of styling to your table, so you need to import that between the `<head>` and `</head>` tags in your webpage HTML too. Here's the line:

`<link rel="stylesheet" type="text/css" href="//cdn.datatables.net/1.10.12/css/jquery.dataTables.min.css">`

## Add your data in a HTML table

To make a searchable, sortable table you need to have a normal HTML table first. This will then be 'targeted' by some extra code we'll write in a moment, and turned into a more interactive table using the code that already exists in the DataTables library. Again, you can use Tableizer if you need to do this quickly ([see previous tutorial](https://github.com/paulbradshaw/tables) for a recap).

## Make sure your table has `<thead>` tags around your headings row

DataTables will only work if the first row containing the headings is placed within `<thead>` and `</thead>`. These tags - which come before and after the `<tr>` tags for the first row - indicate that the row in question is the heading section of the table. Here is an example:

`<thead><tr><th>University</th><th>Total spend on art</th></tr></thead>`

You'll also notice that the table cells use `<th>` rather than `<td>`, because they do not contain table *data* (td) but table *headings* (th).

The rest of the table should be contained within `<tbody>` tags to indicate that they represent the body of the table, i.e. the actual data itself. `<tbody>` goes before the first `<tr>` tag of that data, and then after the *last* row closes with `</tr>` you close `</tbody>`.

If you have a grand totals row you can put that within `<tfoot>` to distinguish that from the body. You can [find out more about these tags here](http://www.w3schools.com/tags/tag_thead.asp).

## Add the attribute to your table

Now, in order to affect this table we need to give it an *attribute* we can describe. Typically this is either an `id=` attribute (if you only have one) or a `class=` attribute (if there's more than one: but bear in mind that *all* items with that class will be affected.)

At the start of your HTML table, then, change the `<table>` tag so that it has an id attribute like so: 

`<table id="data">`

It doesn't have to be called `data`: that's just what we'll use in the example code below.

## Add the JavaScript which targets the table

Now we have everything in place to target the table and apply the powers given us by DataTables. 

In the body of your HTML then (in other words, anywhere between `<body>` and `</body>` - most likely after your table), you need to type some actual JavaScript. Here's the code in full - then I'll break it down and explain it:

`<script type="text/javascript">`

`$(document).ready(function(){`

`  $('#data').DataTable();`

`});`

`</script>`

It's not a huge amount of code - and you could just copy and paste it as long as your table always has the same `id=` value. But hey, why not understand what it's doing. Here goes:

The first and last lines simply identify the code that follows as JavaScript: `<script type="text/javascript">` starts it and `</script>` ends it.

The next line uses the jQuery library to tell the webpage to do something when it's loaded. This ['document ready'](https://learn.jquery.com/using-jquery-core/document-ready/) command is extremely common in jQuery: it basically ensures that the code waits until the page is fully loaded before running the code that comes next. 

Why? Well, if your code is trying to target a HTML table and the table doesn't yet exist (because the page hasn't loaded), then it won't work.

`$(document).ready(function(){`

Here's more detail on that line:

* `$` means 'jQuery'. Anything in parentheses after the `$` is turned into a jQuery 'object', which you have to do in order to use jQuery functions and methods on them. That's exactly what happens here...
* `document` is the HTML page itself. So `$(document)` turns the webpage into a jQuery object.
* `.ready(` will run whatever comes in parentheses after it *once the document is ready* (loaded). Note, by the way, that the parenthesis is not closed on this line, so we'll need to close it at some point later.
* `function(){` describes a *new* function that, once the document is ready, you want to run. Any ingredients will be contained within parentheses, but in this case the parentheses are empty because we don't need any ingredients. Instructions for what the function actually *does* then come within curly brackets. Note again that those aren't yet closed, so we'll need to close this curly bracket as well as the parenthesis.

The main line to focus on is what comes next:

`  $('#data').DataTable();`

This targets our existing HTML table and applies the DataTable function to it. In more detail:

* `$` again means we are turning anything in brackets after it into a jQuery 'object'. In this case it's anything with an `id='data'`: in other words our `<table id='data'>`. The hash symbol means `id=`. (If you were targeting `class=` you would use a period `.` before the class name like so: `$('.data')`
* `.DataTable()` is then applied to that jQuery object (the table with that `id`)

The result of this short line is that the table should now show all the extra interactivity we want. But first, we need to close that parenthesis and curly bracket before we forget:

`});`

The semi-colon is a little [JavaScript convention to mark the end of a line](https://www.codecademy.com/blog/78).

