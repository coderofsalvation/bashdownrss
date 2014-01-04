bashdownrss
===========

portable/easy way of generating of rssfeeds using commandline (piping) using 100% bash and bashdown templates


Usage
=====

    $ ./bashdownrss 
    
      Usage: 

        add:        echo "some message" | bashdownrss your.rss [title] [link]
        reset:      bashdownrss reset your.rss
        print:      bashdownrss generate your.rss

Examples
========

Here's how easy it is to add items to a RSS feed:

    echo "Foo happened" | ./bashdownrss add myfeed.rss
    echo "Bar happened" | ./bashdownrss add myfeed.rss "Announcement title" "http://some.link.com"

And here's how to generate the RSS feed:

    RSSTITLE="my feed" RSSLINK="http://mysite.com" RSSDESC="lorem ipsum"  ./bashdownrss print myfeed.rss > /var/www/foo/myfeed.rss

One doesnt have to be an Einstein to figure this makes it perfect for crontab and *any* kind of applications..since its bash :)

Requirements
============

* written in +/- 50 lines of bash, the ultimate swiss army knife 

Credits
=======

* [bash(down) template 'engine'](https://github.com/coderofsalvation/bashdown)
