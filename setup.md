

Website created with Jekyll.

I followed [this tutorial](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll?platform=linux).
I needed to apply [this fix](https://github.com/jekyll/jekyll/issues/8523) when using `jekyll serve`.

Github-pages themes are not up-to-date. Therefore, I used the [jekyll-remote-theme](https://github.com/benbalter/jekyll-remote-theme) plugin.

## Installation

I used [asdf](https://asdf-vm.com/guide/getting-started.html) to install ruby
```
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
```

Test with the following commands (each should return a version)
```
ruby -v
gem -v
gcc -v
g++ -v
make -v
```

## Testing locally

If testing locally, don't forget to regularly update github-pages: `bundle update github-pages`.

To run a local server, execute `bundle exec jekyll serve`