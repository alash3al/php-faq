---
title: "How to detect ISP with PHP?"
read_time: "1 min"
updated: "october 22, 2014"
---

Getting ISP (internet service provider) of a client is possible with using [gethostbyaddr](http://php.net/gethostbyaddr) function which
will attempt to retrieve clien't host by its IP address:

Simple example:

{% highlight php %}
<?php

$hostname = gethostbyaddr($_SERVER['REMOTE_ADDR']);

echo $hostname;
{% endhighlight %}

But important for you to know is that relying on this is not always possible since the client may be logged in through VPN.
