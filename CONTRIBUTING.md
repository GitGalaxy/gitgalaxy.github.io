Contributing to Git Galaxy's blog
---

We welcome contribution from absolutely anyone who would like to put their work up on Git Galaxy. 

First, fork the repository then clone it

```
git clone git@github.com:your-username/gitgalaxy.github.io.git
```

And then write an article in `_posts/`, using markdown and following the YYYY-MM-DD-Title format for the file (please read more into [writing posts for Jekyll](https://jekyllrb.com/docs/posts/)). Push back to your repository and make a new pull request, with the title being the title of your post, and the body a short summary.

Also be sure to add yourself to `_data/authors.yml` so we can properly credit you.

From there, we'll take a look at your post, and merge it as soon as possible (we recommend setting the date slightly in advance).

If you want to preview the post, or make other changes to the site, install the dependencies

[You'll need jekyll](https://jekyllrb.com/docs/installation/)

```
bundle install
```

Then run the Jekyll server

```
jekyll serve
```

Please read more into [how to tag and categorise posts](https://github.com/GitGalaxy/gitgalaxy.github.io/wiki/Categories-and-Tagging), and read through some existing articles to get a better idea of what we're looking for.