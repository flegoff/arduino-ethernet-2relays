2relays - 2outputWeb
====================

This page is best served behind a ReverseProxy doing all the Access-Control logic.
You don't want anyone to be able to pilot your things, or, maybe you do.

You will need your server to serve an index page :

    <html>
    <body>
        <a href="/openthedoor">Sesame, ouvre-toi !</a>
    </body>
    </html>

And something in the spirit of the following line in your httpd server :

    <Directory /var/www/>
        (...)
        RewriteEngine On
        RewriteBase   /
        RewriteRule ^/openthedoor http://10.42.254.250/openthedoor [P]
    </Directory>

Feel free to help me enhance this with your contributions.