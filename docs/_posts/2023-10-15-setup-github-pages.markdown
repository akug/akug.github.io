---
layout: post
title:  "First post - How to setup github-pages"
date:   2023-10-15 09:27:51 +0200
categories: general
---

Hey it's me, Alex.
Welcome to my website!
I created this website mostly to showcase my PhD and what I am currently working on.

To start off, I thought it makes sense to document how I set up this site.
In general, it is pretty convenient nowadays to use github-pages.
I followed [this tutorial](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll?platform=linux)
to create the site.
I needed to apply [this fix](https://github.com/jekyll/jekyll/issues/8523) when using `jekyll serve` to test the site locally.
Also, I learned that github-pages themes are not up-to-date.
Therefore, I used the [jekyll-remote-theme](https://github.com/benbalter/jekyll-remote-theme) plugin.

## Installation

I used [asdf](https://asdf-vm.com/guide/getting-started.html) to install ruby
{% highlight bash %}
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.13.1
echo '. "$HOME/.asdf/asdf.sh"' >> ~/.bashrc
echo '. "$HOME/.asdf/completions/asdf.bash"' >> ~/.bashrc
# restart terminal
asdf plugin add ruby
asdf plugin add nodejs
asdf install ruby 3.2.2 # this can take some time
asdf global ruby 3.2.2
gem update --system
gem install bundler jekyll
{% endhighlight %}

Test with the following commands (each should return a version)
{% highlight bash %}
ruby -v
gem -v
gcc -v
g++ -v
make -v
{% endhighlight %}

## Testing locally

If testing locally, don't forget to regularly update github-pages: `bundle update github-pages`.

To run a local server, execute `bundle exec jekyll serve`.


## Modifications to the layout

I use the minimal layout (`remote_theme: jekyll/minima` in `_config.yml`), and changed the layout of `index.markdown` to page.
The blog is an additional `blog.markdown` with layout `home`.
