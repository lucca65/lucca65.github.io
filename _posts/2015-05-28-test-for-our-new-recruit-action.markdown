---
layout: post
title: Test for our new Recruit action
published: false
categories:
---

{% highlight ruby linenos %}
#  ________________________________________ 
# / We are looking for Developers! Are you \
# | up to it?                              |
# |                                        |
# \ Kiik                                   /
#  ---------------------------------------- 
#         \   ^__^
#          \  (oo)\_______
#             (__)\       )\/\
#                 ||----w |
#                 ||     ||
 
class Developer
  attr_acessor :interests, :knowledge, :experience
end
 
# That's you!!
dev = Developer.new
 
requirements  = [:oop, :git, :linux, :passion]
our_interests = [:functional_programming, :ruby, :devops, :golang]
 
fits = requirements.all? { |requirement| dev.knowledge.include?(requirement) }
extra = our_interests.count { |our_interest|dev.interests.include?(our_interest) }
 
send_cv(dev)
# If you know what we mean by this code, send us your CV, portifolio or Github!
{% endhighlight %}

