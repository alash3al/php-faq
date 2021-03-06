---
title: "$_GET vs $_POST?"
read_time: "1 min"
updated: "october 22, 2014"
---

Users often ask what are the differences between the $_GET and $_POST variables in PHP and GET and POST HTTP methods in general.

First some background on the HTTP methods. GET and POST are two of many HTTP methods (GET, HEAD, POST, PUT, DELETE, TRACE, OPTIONS, CONNECT and PATCH)
used to indicate the desired action to be performed on the identified resourse.

#### GET method:

Query strings are sent in the URL of the GET request:

{% highlight php %}
/test/form.php?name1=value1&name2=value2&name3=value3
{% endhighlight %}

You can than get the query strings in PHP like this:

{% highlight php %}
<?php

$name1 = filter_has_var(INPUT_GET, 'name1') ? filter_input(INPUT_GET, 'name1', FILTER_SANITIZE_STRING) : false;
{% endhighlight %}

#### POST method:

In case of POST method query strings are sent in the HTTP message body of the POST request:

{% highlight php %}
POST /test/form.php HTTP/1.1
Host: test.com
name1=value1&name2=value2&name3=value3
{% endhighlight %}

Query strings from POST method can be than processed in PHP like this:

{% highlight php %}
<?php

$name1 = filter_has_var(INPUT_POST, 'name1') ? filter_input(INPUT_POST, 'name1', FILTER_SANITIZE_STRING) : false;

{% endhighlight %}
