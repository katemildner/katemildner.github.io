---
layout: post
title:  "Jekyll quickstart - part one"
date:   2020-01-23 09:00:00 +0100
categories: jekyll quickstart
---

**_This will be the first and most certainly not last post about how-to- and how-not-to-jekyll. By no means will it be an exhaustive compendium about Jekylling, yet you can at least learn from my mistakes. Brace yourself for messy blogging._**

### **Jekyll out-of-the-box: don't touch it**
If you are like me and creating a static site is just a means to an end - I have a piece of advice: don't overdo it. _Do **not** overdo it._ Also: don't touch the themes until you are ready to mingle with some unexpected issues. I know - it looks like it's simple and fun and easy - it's not. I'm not saying it's not possible to achieve - I'm merely remarking on how disappointing the advertising is. :)

Just run this:

`jekyll new myblogorwhatever`

push it to GitHub as _yourghprofilename.github.io_ repository, master branch only, enable GitHub Pages and you have created yourself a tiny blog. Maybe fill out the necessities in `_config.yml` like title, your email and description, maybe write a post. Call it a day.

### **But what if you are already too deep?**
Jekyll out-of-the-box worked for me just fine, but then I saw this in my Gemfile:

{% highlight ruby %}
gem "jekyll", "~> 4.0.0"
# If you want to use GitHub Pages, remove the "gem "jekyll"" above and
# uncomment the line below. To upgrade, run `bundle update github-pages`.
# gem "github-pages", group: :jekyll_plugins
{% endhighlight %}

And boy, how excited I got - using GitHub Pages was exactly what I needed. So I did what was suggested not by Stack Overflow, not by some random Google search, but by my very own Gemfile.

```
Bundler could not find compatible versions for gem "jekyll-feed":
  In snapshot (Gemfile.lock):
    jekyll-feed (= 0.13.0)

  In Gemfile:
    github-pages was resolved to 36, which depends on
      jekyll-feed (= 0.2.3)

    minima (~> 2.5) was resolved to 2.5.1, which depends on
      jekyll-feed (~> 0.9)

Running 'bundle update' will rebuild your snapshot from scratch, using only
the gems in your Gemfile, which may resolve the conflict.
```
Oof, off to a great start.
Unencumbered I ran `bundle update` - no hiccups there.
Locally everything looked promising. So I pushed it on the new gh-pages branch. For various reasons I did not bother to use the _itsyehudit.github.io_ name for my repo, and went with the original title of _placeholder_blog_.

Then I decided to change the theme, which seemed easy enough: _install the gem-based theme of your choice, change the theme in the `_config` file_ and that's it.

It was not. I tried other themes - that's when the true dependency hell mentioned in the first post broke loose. There was more trouble ahead as well.
Also: my page did not show up online.

There were a few mistakes, that in various combinations made me think various things went wrong. I won't entertain you with the story of me going back and forth trying to figure out what failed. If you just want a **quick setup without any hassle**, try this:

1. Install Jekyll<sup>**a**</sup>:<br/>
`gem install jekyll`
2. Generate your website:<br/>
`jekyll new mywebsite`
3. For the fastest result name your remote repository yourghprofilename.github.io<sup>**b**</sup>
4. Link your local repo to it's remote counterpart
5. Enable GitHub Pages in your repository's Settings on GitHub by choosing master branch as the source for your webpage
6. Fill out everything you wish in `_config` and `about`, write a post in `_posts`, your choice
7. Try `bundle exec jekyll serve` to check it out locally on `http://localhost:4000`
8. Commit all this hard work
9. `git push origin master`
10. After a while (GitHub takes its time to build your website, don't panic yet) check it out under `http://yourghprofilename.github.io`

And that's it. I've mentioned the github-pages gem, but I really don't think it's crucial, nonetheless the more I know the more I'll share here. Same goes for themes.

**a** - if you don't have bundler - install it as well: `gem install bundler`<br/>
**b** - if you are certain you'd prefer something like: _yourghprofilename.github.io/my_blog_ remember to name your online repository just as _my_blog_, add _my_blog_ to the `baseurl:` in `_config`. Also choose the branch accordingly for your GitHub Page source - pay attention on which branch you are pushing your changes. You can choose from gh-pages, master or master/docs.

But what to do when you truly are quite deep into the project, with some plugins or themes installed, multiple errors or dependency issues on your head? If the content is what matters the most to you - scrap it. Start over. Backup your posts, and just let yourself get a clean start. At least that's what I did - and here we are! ;)
