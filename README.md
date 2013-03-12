moment-cli
==========

CLI for printing dates via [momentjs](http://momentjs.com/).

Install
-------

```
$ npm install -g moment-cli
```

Usage
-----

```
$ moment --help

  Usage: moment <input> [options]

  Options:

    -h, --help                 output usage information
    -V, --version              output the version number
    -i, --inputFormat <format>  e.g: "MM-DD-YYYY". Special handling for "unix".
    -f, --format <format>       Output format. See momentjs docs for options.
    -t, --timeago               Output in `timeago` format (fromNow).
    -c, --calendar              Output in `calendar` format.
    -u, --unix                  Output a unix timestamp (secs since Epoch).
    -j, --js                    Ouput a JavaScript timestamp (ms since Epoch).
```

Examples
--------

**Output current time**

```
$ moment
2013-03-11T16:45:21-07:00
```

**Output current time in a custom format**

```
$ moment -f "dddd, MMMM Do YYYY, h:mm:ss a"
Monday, March 11th 2013, 4:46:42 pm
```

**Convert a JavaScript timestamp (ms since Epoch) to a custom format**

```
$ moment 1318781876406 -f MM/DD/YYYY
10/16/2011
```

**Convert a Unix timestamp to a formatted date**

```
$ moment 1318781876 -i unix
2011-10-16T09:17:56-07:00
```

**Convert a date string into a JavaScript timestamp**

```
$ moment 03/11/2011
1299830400000
```

**Convert a date string into a unix timestamp**

```
$ moment 03/11/2011 -u
1299830400
```

Formatting Cheat-sheet
----------------------

<table>
  <tbody>
    <tr>
      <th></th>
      <th>Token</th>
      <th>Output</th>
    </tr>
    <tr>
      <td><b>Month</b></td>
      <td>M</td>
      <td>1 2 ... 11 12</td>
    </tr>
    <tr>
      <td></td>
      <td>Mo</td>
      <td>1st 2nd ... 11th 12th</td>
    </tr>
    <tr>
      <td></td>
      <td>MM</td>
      <td>01 02 ... 11 12</td>
    </tr>
    <tr>
      <td></td>
      <td>MMM</td>
      <td>Jan Feb ... Nov Dec</td>
    </tr>
    <tr>
      <td></td>
      <td>MMMM</td>
      <td>January February ... November December</td>
    </tr>
    <tr>
      <td><b>Day of Month</b></td>
      <td>D</td>
      <td>1 2 ... 30 30</td>
    </tr>
    <tr>
      <td></td>
      <td>Do</td>
      <td>1st 2nd ... 30th 31st</td>
    </tr>
    <tr>
      <td></td>
      <td>DD</td>
      <td>01 02 ... 30 31</td>
    </tr>
    <tr>
      <td><b>Day of Year</b></td>
      <td>DDD</td>
      <td>1 2 ... 364 365</td>
    </tr>
    <tr>
      <td></td>
      <td>DDDo</td>
      <td>1st 2nd ... 364th 365th</td>
    </tr>
    <tr>
      <td></td>
      <td>DDDD</td>
      <td>001 002 ... 364 365</td>
    </tr>
    <tr>
      <td><b>Day of Week</b></td>
      <td>d</td>
      <td>0 1 ... 5 6</td>
    </tr>
    <tr>
      <td></td>
      <td>do</td>
      <td>0th 1st ... 5th 6th</td>
    </tr>
    <tr>
      <td></td>
      <td>ddd</td>
      <td>Sun Mon ... Fri Sat</td>
    </tr>
    <tr>
      <td></td>
      <td>dddd</td>
      <td>Sunday Monday ... Friday Saturday</td>
    </tr>
    <tr>
      <td><b>Week of Year</b></td>
      <td>w</td>
      <td>1 2 ... 52 53</td>
    </tr>
    <tr>
      <td></td>
      <td>wo</td>
      <td>1st 2nd ... 52nd 53rd</td>
    </tr>
    <tr>
      <td></td>
      <td>ww</td>
      <td>01 02 ... 52 53</td>
    </tr>
    <tr>
      <td><b>ISO Week of Year</b></td>
      <td>W</td>
      <td>1 2 ... 52 53</td>
    </tr>
    <tr>
      <td></td>
      <td>Wo</td>
      <td>1st 2nd ... 52nd 53rd</td>
    </tr>
    <tr>
      <td></td>
      <td>WW</td>
      <td>01 02 ... 52 53</td>
    </tr>
    <tr>
      <td><b>Year</b></td>
      <td>YY</td>
      <td>70 71 ... 29 30</td>
    </tr>
    <tr>
      <td></td>
      <td>YYYY</td>
      <td>1970 1971 ... 2029 2030</td>
    </tr>
    <tr>
      <td><b>AM/PM</b></td>
      <td>A</td>
      <td>AM PM</td>
    </tr>
    <tr>
      <td></td>
      <td>a</td>
      <td>am pm</td>
    </tr>
    <tr>
      <td><b>Hour</b></td>
      <td>H</td>
      <td>0 1 ... 22 23</td>
    </tr>
    <tr>
      <td></td>
      <td>HH</td>
      <td>00 01 ... 22 23</td>
    </tr>
    <tr>
      <td></td>
      <td>h</td>
      <td>1 2 ... 11 12</td>
    </tr>
    <tr>
      <td></td>
      <td>hh</td>
      <td>01 02 ... 11 12</td>
    </tr>
    <tr>
      <td><b>Minute</b></td>
      <td>m</td>
      <td>0 1 ... 58 59</td>
    </tr>
    <tr>
      <td></td>
      <td>mm</td>
      <td>00 01 ... 58 59</td>
    </tr>
    <tr>
      <td><b>Second</b></td>
      <td>s</td>
      <td>0 1 ... 58 59</td>
    </tr>
    <tr>
      <td></td>
      <td>ss</td>
      <td>00 01 ... 58 59</td>
    </tr>
    <tr>
      <td><b>Fractional Second</b></td>
      <td>S</td>
      <td>0 1 ... 8 9</td>
    </tr>
    <tr>
      <td></td>
      <td>SS</td>
      <td>0 1 ... 98 99</td>
    </tr>
    <tr>
      <td></td>
      <td>SSS</td>
      <td>0 1 ... 998 999</td>
    </tr>
    <tr>
      <td></td>
      <td>ss</td>
      <td>00 01 ... 58 59</td>
    </tr>
    <tr>
      <td><b>Timezone</b></td>
      <td>z or zz</td>
      <td>
        EST CST ... MST PST
        <br/>
        <b>Note:</b> as of <b>1.6.0</b>, the z/zz format tokens have been deprecated. <a href="https://github.com/timrwood/moment/issues/162">Read more about it here.</a>
      </td>
    </tr>
    <tr>
      <td></td>
      <td>Z</td>
      <td>-07:00 -06:00 ... +06:00 +07:00</td>
    </tr>
    <tr>
      <td></td>
      <td>ZZ</td>
      <td>
        -0700 -0600 ... +0600 +0700
      </td>
    </tr>
    <tr>
      <td><b>Unix Timestamp</b></td>
      <td>X</td>
      <td>1360013296</td>
    </tr>
  </tbody>
</table>


- - -

### Developed by [Terra Eclipse](http://www.terraeclipse.com)
Terra Eclipse, Inc. is a nationally recognized political technology and
strategy firm located in Aptos, CA and Washington, D.C.

- - -

### License: MIT
Copyright (C) 2012 Terra Eclipse, Inc. ([http://www.terraeclipse.com](http://www.terraeclipse.com))

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the &quot;Software&quot;), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished
to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED &quot;AS IS&quot;, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
