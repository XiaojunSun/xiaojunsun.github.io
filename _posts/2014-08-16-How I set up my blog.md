---
layout: post
title:  "How do I set up my blog with GitHub Pages and Jekyll"
date:   2014-8-16 17:17:59
categories: 
- Tutorial
tags:
- Jekyll
- GitHub

---

Hello! I'm Xiaojun. This is my blog on github.

I build my blog with GitHub Pages and Jekyll. I forked [Danny Li's blog](http://dannyli.net) and referred to [his post][1] and [Madhur's blog][3]. Here I introduced the procedures to set up a blog like mine.

You need install [Ruby][4] and [DevKit][5]. Be careful that no space is allowed in the path where you install them. They need not to be in the same directory.

Open command prompt with Ruby. 

```
cd C:\Ruby193
ruby --version
```

If the output is normal, then

```
cd C:\devkit
ruby dk.rb init
```

to generate the config.yml file to be used later in this Step. Then

```
ruby dk.rb install
gem install jekyll
```

`gem install jekyll` is easy to go wrong. Be patient and give more try.


Download [ez_setup.py][2], double click to install it. Given that you have create you GitHub page and clone it on your PC with the name `yourname.github.io`. Copy the files in the repo you forked after you having removed all useless information in that repo.

```
cd yourname.github.io
jekyll serve
```

Now browse to <http://localhost:4000> to see you blog.

Remenber to include `_site/*` in your `.gitignore` file.


[2]: https://bootstrap.pypa.io/ez_setup.py
[1]: http://dannyli.net/notes/fix-problems-of-jekyll-on-windows/
[3]: http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html
[4]: http://dl.bintray.com/oneclick/rubyinstaller/rubyinstaller-1.9.3-p448.exe?direct
[5]: https://github.com/downloads/oneclick/rubyinstaller/DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe