---
title: Marketo Form Reset
date: '2016-06-14 00:00:00'
categories: blog
layout: blog-post
img: "/forestryio/images/better-forms.jpg"
alt: Better Marketo Forms
tags:
- Marketo
featured_image: ''
permalink: "/blog/:title/"
lead-text: Say goodbye to your ugly Marketo embedded forms
slug: marketo-form-reset
---
<p>A complaint I hear from most clients using Marketo is that they have ugly form stylings for their embedded forms. 
Also developers have a hard time styling the forms because Marketo doesn't use the most friendly code for the display of their forms. </p>

<p>I made a Marketo form reset so you have a styling baseline on your embedded forms. 
This will help you style your form to match your own companies styleguides without having Marketo's opinionated stylings override your CSS.</p>

<p>Just copy the code below and go to your form in Marketo. <br/>
Then Edit Form > Form Settings > Click "Gear" icon > Edit Custom CSS<br/>
Paste the code into the window and save it. </p>
<img src="../../img/blog/form-css.png" class="img-responsive" />

{% highlight ruby %}

/* Marketo Form Reset by Alex Wu - June 2016 */

.mktoForm .mktoRequiredField label.mktoLabel {
    font-weight:normal !important;
}

.mktoForm input[type=text], .mktoForm input[type=url], .mktoForm input[type=email], .mktoForm input[type=tel], .mktoForm input[type=number], .mktoForm input[type=date], .mktoForm textarea.mktoField, .mktoForm select.mktoField {
    width:100% !important;
}
.mktoFormCol, .mktoFieldWrap {
    width:100% !important;
}

.mktoForm .mktoOffset {
    float: left;
    height:0 !important;
    width:10px;
}

.mktoButtonRow {
  width:100% !important;
  text-align:center;
}

.mktoForm.mktoLayoutAbove .mktoRadioList, .mktoForm.mktoLayoutAbove .mktoCheckboxList {
  width:auto !important;
  float:left !important;
  clear:none !important;
}

{% endhighlight %}