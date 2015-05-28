---
layout: post
title: Rakefile for new posts in Jekyll
published: true
categories: ruby jekyll
---

When creating this blog, I've came across this problem that there isn't really
an easy way to create new posts. So I've searched a little and found a solution
by
  <a href="https://twitter.com/avdgaag" target="_blank">
    @avdgaag
  </a>
 (which you can find
   <a href="http://arjanvandergaag.nl/blog/creating-new-jekyll-posts.html" target="_blank">here</a>)

It wasn't easy as I would expect, it asked me to use `rake TITLE="New post"`,
and it seems wrong. so I've changed the way we ask for a title.

after change a new post is much clearer. To achieve that just add the
`Rakefile` to your Jekyll blog, and call it:

{% highlight sh linenos %}
  $ rake post
  Whats the title of your post?
  My first automated blog post

  Post "Post 'My first automated blog post' created successfully!" created successfully!
{% endhighlight %}

Our code for that is basically a rake task:

{% highlight ruby linenos %}
desc 'Create a new draft post'
task :post do
  # asks for user
  STDOUT.puts('Whats the title of your post?')
  title = STDIN.gets.chomp

  # ... logic to validate entry

  # file name, where we use title
  slug = "#{Date.today}-#{title.downcase.gsub(/[^\w]+/, '-')}"

  # ...logic to create .markdown file

end
{% endhighlight %}

You can use this rake on your project, enjoy. Don't forget to check it out on
  <a href="https://gist.github.com/lucca65/7d8692788932a935e881" target="_blank" >
    Gist
  </a> for it!
