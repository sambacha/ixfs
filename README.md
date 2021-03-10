ixfs
================

HTTP POST files here:   <br>
 `   curl -F'file=@yourfile.png' {0}`   <br>
You can also POST remote URLs:    <br>
`    curl -F'url=http://example.com/image.jpg' {0} `  <br>
Or you can shorten URLs:  <br>
 `   curl -F'shorten=http://example.com/some/long/url' {0} ` <br>
File URLs are valid for at least 30 days and up to a year (see below).  <br>
Shortened URLs do not expire.  <br>
Maximum file size: {1}  <br>
Not allowed: {5}  <br>


FILE RETENTION PERIOD
---------------------

```katex
retention = min_age + (-max_age + min_age) * pow((file_size / max_size - 1), 3)
```
<pre>
   days
    365 |  \\
        |   \\
        |    \\
        |     \\
        |      \\
        |       \\
        |        ..
        |          \\
  197.5 | ----------..-------------------------------------------
        |             ..
        |               \\
        |                ..
        |                  ...
        |                     ..
        |                       ...
        |                          ....
        |                              ......
     30 |                                    ....................
          0{2}{3}
           {4}
</pre>
