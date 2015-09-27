---
layout: post
title: params; Simplifying Params
date: 2015-08-10 15:27:31
---

I have been developing and using R packages to wrangl genomics data for a few years. Often we have a huge list of parameters including paths to apps, their default parameters and reference genomes and other related files. While its possible to use R's default `options()` function to manage these, often the space becomes quite cluttered. 

We developed a small nifty package params, which reads configuration files and loads there parameters into R. This attempts to solve 3 things, 
1. easy reading and loading of parameters [`load_opts()`]
2. dynamic changing of params [`set_opts()`]
3. fetching and pretty printing of params [`get_opts()`]


1. easy reading of conf files, automatic recognition and reading of param files:
	a. conf/tsv/tab/txt: tab delimited
	b. csv: comma separated
	c. xlsx: microsoft excel files (not recommended)
	
2. set_opts(): 



{% highlight r %}
install.packages("params")
{% endhighlight %}