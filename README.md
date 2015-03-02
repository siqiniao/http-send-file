# HTTP send file

Sends a file with support for (multiple) range requests. 
It is able to throttle the download.
It is quite small and simple.

This class resembles the php http_send_file from PHP pecl

See: 

<http://php.net/manual/en/function.http-send-file.php> 

Install

Usage example: 

~~~php

        use diversen\sendfile;
        $s = new sendfile();
        
        // if you don't set type - we will try to guess it
        $s->contentType('application/epub+zip');
        
        // if you don't set disposition (file name user agent will see)
        // we will make a file name from file
        $s->contentDisposition('argh.epub');
        
        // chunks of 40960 bytes per 0.1 secs
        // if you don't set this then the values below are the defaults
        // approx 409600 bytes per sec
        $s->throttle(0.1, 40960);

        // send the file
        $s->send($file);
~~~

# Credits 

Much of the code is taken (and rewritten) from here: 

<http://w-shadow.com/blog/2007/08/12/how-to-force-file-download-with-php/>

The process is nicely explained here: 

<http://www.media-division.com/the-right-way-to-handle-file-downloads-in-php/>
