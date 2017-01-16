---
title: Best Way To Put Marketo Forms Onto Website
date: '2017-01-16 18:19:18'
permalink: "/blog/:title/"
layout: blog-post
categories:
- blog
- marketo
tags:
- Marketo
img: "/forestryio/images/iframe-forms.jpg"
alt: image
featured_image: image.jpg
lead-text: Iframes are bad, but it gets the job done.
---
There has been a lot of debate in the community on what is the best method to insert your Marketo forms into your website/CMS. After a lot of research on the topic, I think the best method is to *use an iframe to embed the form*. I know a lot of developers will scoff at this idea because using iframes is a big no-no if you want clean code on your site. 

The reason we want to use an iframe is because we want to preserve the pre-fill functionality when your visitor hits the page. Marketo cookies the visitor and if they've already filled out one of your forms previously, their information will pre-populate in the form fields. This feature reduces friction for the user and increases the conversion rate. This functionality does not work if you use the form embed code or the Marketo API. The user has to hit a Marketo landing page with the form on it. Inside the iframe window is a Marketo landing page with just the form on it. The rest of the page/layout is still your original design and site. Also, another big plus, is that since we are using a physical Marketo form that you can see in your Marketo instance, you can edit the form freely inside Marketo, and see all of your form fills. You won't have a blackbox if you use the API, that also limits your calls to 1-10k per day (forgot the actual number).

One issue with the iframe method is that it will load the iframe twice, which would mess up your analytics and tracking. Luckily I've found a fix for this and will be detailing how to use it below. 


============Solution Overview=============

Instead of having the iframe on the page when the page first loads, I made the iframe dynamically with javascript that assigns the src URL of the iframe at the same time its created. Then I attach the created iframe to the container of the iframe within the website.

===============Step 1====================

First you need to insert this HTML snippet into where you want the code on your website. Note to change out the URL of your actual URL of the landing page with the Marketo form. 

~~~
<div id="marketoFrame" data-src="https://mkto.your-landing-page-url-location.html"></div>
~~~

===============Step ​2​====================

Insert this javascript code onto your website. 

~~~
<script type="text/javascript">
var iframeContainer = document.getElementById('marketoFrame');

var iframeSrc = iframeContainer.getAttribute("data-src");
var loc = window.location.toString(),
    params = loc.split('?')[1],
    iframe = document.createElement('iframe');

iframe.setAttribute("src", iframeSrc + '?' + params);

iframe.style.height = "875px";
iframe.style.width = "100%";
iframeContainer.appendChild(iframe);
</script>
~~~