#ur1ca.py

##NAME

`ur1ca.py`

##SYNOPSIS

    ur1ca.py FULL_URL

##DESCRIPTION

`ur1ca.py` is a command-line ur1.ca client.

[ur1.ca](http://ur1.ca/) is a URL shortening services provided by
[status.net](http://status.net).  The `ur1ca.py` script makes it possible to
access the service from the command line.  This is done by scraping the
returned page and look for the shortened URL.

When a shortened URL is successfully obtained, it is written to the standard
output.

If the ur1.ca service responds but fails to return a shortened URL, the
program exits with status 1 and nothing is written to the output.

The provided full URL must contain a scheme part (such as `http://`).  The
ur1.ca service only accepts `http://` and `https://` schemes.  As a result,
the program rejects any URL with other schemes (or ones without a scheme at
all), and doesn't even attempt to contact the ur1.ca server.  Invalid input
is rejected with exit code 2.

Error messages, if any, are written to the standard error.

##EXIT CODE

* 0:  The program exits successfully.
* 1:  ur1.ca service fails to shorten the long URL.
* 2:  Input full URL is rejected as invalid.

##ENVIRONMENT

* `http_proxy`: HTTP proxy server.

##EXAMPLE

* `./ur1ca.py https://github.com/congma/ur1ca.py/`  
  Shorten a full URL.
* ``for url in `cat url_list.txt`; do ./ur1ca.py $url >> short_urls.txt; sleep 2s; done ``  
  Shorten multiple URLs (play nice with the server).

##SEE ALSO

* [http://ur1.ca/](http://ur1.ca "ur1 generator")
* [http://status.net/](http://status.net/ "Status.net")

##AVAILABILITY

[https://github.com/congma/ur1ca.py/](https://github.com/congma/ur1ca.py/)
