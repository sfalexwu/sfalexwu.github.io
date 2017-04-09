---
title: Case Study Ximble Wordpress to Jekyll Migration
date: '2017-04-08 18:19:18'
permalink: "/blog/:title/"
layout: blog-post
categories:
- blog
- webdev
tags:
- webdev
img: "/images/ximble-hp.jpg"
alt: ximble
featured_image: image.jpg
lead-text: Learn what I used to migrate a Wordpress site to a modern day Jekyll static site
---
See the <a href="https://www.ximble.com/">Ximble Site</a>.

Peter the CTO from Nimbleschedule called me to discuss a complete re-brand of their popular Staff Scheduling and
time-clock software. At first, he wanted to revamp their current Wordpress site with all new branding and designs. It
made sense, they've always used Wordpress, he had over 400 posts dating all the way back to 2011. It was slow,
bloated, and required constant maintenance to keep it secure. They didn't particularly like it, but this was just how
 it was.

I told Peter about the state of static sites these days. It's still relatively new, and not as mature as Wordpress
yet. But, I explained to him the <a href="http://templatestud.io/blog/static-sites-vs-wordpress/">benefits</a> such as
speed, security and simpler architecture. He saw the benefits because he understood the technology; and also he was a
fellow technology geek.

As a person that had to deal with the headaches with CMS's like Joomla, Drupal, and Wordpress, I kindly
declined his offer to work on the site in Wordpress. Instead, I proposed we migrate the whole thing off of Wordpress
onto Jekyll. Start fresh, like buying a new car, instead of trying to slap a new coat of paint on an old clunker.

Peter said yes, and we quickly got to work.

Luckily there was a <a href="https://github.com/benbalter/wordpress-to-jekyll-exporter">Wordpress to Jekyll
exporter</a>, that downloads the current Wordpress posts into markdown format, ready for your Jekyll site. I'm not
going to say the export was 100% clean and ready to plug into Jekyll, but we managed.


![ximble pagespeed](../../images/ximble-pagespeed.png "Ximble"){:class="img-responsive"}

Peter wanted a blazing fast speed, and I was going to give it to him. We used <a href="https://github
.com/Ensighten/spritesmith">spritesmith</a> to package icons/images into a single sprite and provides coordinates for
 the stylesheet. We lazy-loaded the images so they only load when it's needed and took care of the critical fold CSS
 so users will have an optimal viewing experience when they first hit the site. The site was very image heavy so
 these things really helped.

<br/> <br/>
![ximble collections](../../images/ximble-restaurants.png "Ximble collections"){:class="img-responsive"}

The site had a section broken out by <a href="https://www.ximble.com/restaurants/">industry</a> where they displayed
the company's logos of the brands that use them. This was a perfect instance to use Jekyll's collections functionality.

<br/> <br/>
![forestry-io](http://forestry.io/blog//forestryio/images/new-forestry-io-cms.png "Forestry.io"){:class="img-responsive"}

Another big requirement was to have an interface where non-technical marketers can easily create and edit blog posts
without delving into code. Here's where a great tool I found called <a href="https://forestry.io/">Forest.io</a> came
 in handy. Also, they provide excellent customer support if you ever run into anything.


For the blog, we were able to maintain the original post images from the Wordpress site. The authors were recreated
into an authors.yml file with their corresponding thumbnail images, name, and info. Since there were so many blog
posts, we had to implement a pagination feature to easily navigate through the older blog posts. I used the gem
jekyll-paginate to accomplish this.

For the hosting, we went with Netlify. They were able to easily connect with our github repo, so the setup was
extremely easy. Netlify is also able to handle form submissions, so all forms on the site are tied to it. Everything
went pretty smoothly, and we were able to deploy a beautiful marketing site/blog.

Check out the <a href="https://www.ximble.com/">Ximble Site</a>.


