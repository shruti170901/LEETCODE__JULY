---
layout: default
---

{% include 01-name.md %}

<br>

{% include 03-links.md %}

<br>

{% include 04-lists.md %}

<br>

{% include 05-emphasis.md %}

<html>
<div id="contact">
        <h2>Get in Touch</h2>
        <div id="contact-form">
                <form action="https://formspree.io/xjvajvzr" method="POST">
                <input type="hidden" name="_subject" value="Contact request from personal website" />
                <input type="email" name="_replyto" placeholder="Your email" required>
                <textarea name="message" placeholder="Type your message" required></textarea>
                <button type="submit">Send</button>
            </form>
        </div>
    </div>
</html>


<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title></title>
    <style type="text/css">
        .highlighted
        {
            background-color: yellow;
        }
        .highlight
        {
            background-color: #fff34d;
            -moz-border-radius: 5px; /* FF1+ */
            -webkit-border-radius: 5px; /* Saf3-4 */
            border-radius: 5px; /* Opera 10.5, IE 9, Saf5, Chrome */
            -moz-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.7); /* FF3.5+ */
            -webkit-box-shadow: 0 1px 4px rgba(0, 0, 0, 0.7); /* Saf3.0+, Chrome */
            box-shadow: 0 1px 4px rgba(0, 0, 0, 0.7); /* Opera 10.5+, IE 9.0 */
        }
        .highlight
        {
            padding: 1px 4px;
            margin: 0 -4px;
        }
    </style>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js" type="text/javascript"></script>
    <script type="text/javascript">
        function searchAndHighlight(searchTerm, selector) {
            if (searchTerm) {               
                var selector = selector || "#realTimeContents"; //use body as selector if none provided
                var searchTermRegEx = new RegExp(searchTerm, "ig");
                var matches = $(selector).text().match(searchTermRegEx);
                if (matches != null && matches.length > 0) {
                    $('.highlighted').removeClass('highlighted'); //Remove old search highlights 
                    //Remove the previous matches
                    $span = $('#realTimeContents span');
                    $span.replaceWith($span.html());
                    if (searchTerm === "&") {
                        searchTerm = "&amp;";
                        searchTermRegEx = new RegExp(searchTerm, "ig");
                    }
                    $(selector).html($(selector).html().replace(searchTermRegEx, "<span class='match'>" + searchTerm + "</span>"));
                    $('.match:first').addClass('highlighted');
                    var i = 0;
                    $('.next_h').off('click').on('click', function () {
                        i++;
                        if (i >= $('.match').length) i = 0;
                        $('.match').removeClass('highlighted');
                        $('.match').eq(i).addClass('highlighted');
                        $('.ui-mobile-viewport').animate({
                            scrollTop: $('.match').eq(i).offset().top
                        }, 300);
                    });
                    $('.previous_h').off('click').on('click', function () {
                        i--;
                        if (i < 0) i = $('.match').length - 1;
                        $('.match').removeClass('highlighted');
                        $('.match').eq(i).addClass('highlighted');
                        $('.ui-mobile-viewport').animate({
                            scrollTop: $('.match').eq(i).offset().top
                        }, 300);
                    });
                    if ($('.highlighted:first').length) { //if match found, scroll to where the first one appears
                        $(window).scrollTop($('.highlighted:first').position().top);
                    }
                    return true;
                }
            }
            return false;
        }
        $(document).on('click', '.searchButtonClickText_h', function (event) {
            $(".highlighted").removeClass("highlighted").removeClass("match");
            if (!searchAndHighlight($('.textSearchvalue_h').val())) {
                alert("No results found");
            }
        });
    </script>
</head>
<body>
    <div class="searchContend_h">
        <div class="ui-grid-c">
            <div class="ui-block-a">
                <input name="text-12" id="text-12" value="" type="text" class="textSearchvalue_h" />
            </div>
            <div class="ui-block-b">
                <a href="#" class="searchButtonClickText_h">Search</a>
            </div>
            <div class="ui-block-c">
                <a href="#" class="next_h">Next</a>
            </div>
            <div class="ui-block-d">
                <a href="#" class="previous_h">Previous</a>
            </div>
            <div id="realTimeContents">
                https://codextream.github.io/ARRANGING-COINS/
                <br />
                https://codextream.github.io/BINARY-TREE-LEVEL-ORDER-TRAVERSAL-II/
                <br />
                https://codextream.github.io/PRISON-CELLS-AFTER-N-DAYS/
                <br />
                https://codextream.github.io/UGLY-NUMBER-II/
                <br />
                https://codextream.github.io/HAMMING-DISTANCE/
                <br />
                https://codextream.github.io/PLUS-ONE/
                <br />
                https://codextream.github.io/ISLAND-PERIMETER/
                <br />
                https://codextream.github.io/3-SUM/
                <br />
            </div>
        </div>
    </div>
</body>
</html>
