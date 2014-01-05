bashdownrss
===========

portable/easy way of generating of rssfeeds using commandline (piping) using 100% bash and bashdown templates


Usage
=====

    $ ./bashdownrss 
    
      Usage: 

        add:        echo "some message" | bashdownrss add your.rss [title] [link]
        reset:      bashdownrss reset your.rss
        print:      bashdownrss generate your.rss [maxitems]

One doesnt have to be an Einstein to figure this makes it perfect for crontab, fifo/pipe's and *any* kind of applications..since its all bash :)

Example #1
==========

Here's how easy it is to add items to a RSS feed:

    echo "Foo happened" | ./bashdownrss add myfeed.rss
    echo "Bar happened" | ./bashdownrss add myfeed.rss "Announcement title" "http://some.link.com"

And here's how to generate the RSS feed:

    RSSTITLE="my feed" RSSLINK="http://mysite.com" RSSDESC="lorem ipsum"  ./bashdownrss print myfeed.rss > /var/www/foo/myfeed.rss

(optionally you can specify an maxitems, see next example of the 'print' command)

Example #2
==========

put this into your crontab to generate the feed hourly (feel free to modify) with always the latest 10 items:
    
    @hourly RSSTITLE="my feed" RSSLINK="http://mysite.com" RSSDESC="lorem ipsum" /path/to/bashdownrss print errors.rss 10 > /var/www/foo/errors.rss

now with tail(f) you can easily monitor some (log)files etc:

    tailf /some/application/log.txt | grep "ERROR" | ./bashdownrss add errors.rss

This is just a simple example but you'll get the point I guess :)

Requirements
============

* written in +/- 50 lines of bash, the ultimate swiss army knife 

Credits
=======

* [bash(down) template 'engine'](https://github.com/coderofsalvation/bashdown)
