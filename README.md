# Regex
Regex

# [ISO8601](https://en.wikipedia.org/wiki/ISO_8601)

## Dates

> ### Python
> ```regex
> (?P<iso8601_dates>[+-]?(?:\d{2}(?:0[1235679]|[2468][1235679]|[13579][01345789])|(?:0[1235679]|[2468][1235679]|[13579][01345789])00)(?:-(?:(?:36[0-5]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9])|02(?:-(?:2[0-8]|1\d|0[1-9]))?)|02(?:2[0-8]|1\d|0[1-9])|(?:36[0-5]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9]))|(?:[+-]?(?:\d{2}(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|[2468][048]|[13579][26])00)|[+]?0000)(?:-(?:(?:36[0-6]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9])|02(?:-(?:2[0-9]|1\d|0[1-9]))?)|02(?:2[0-9]|1\d|0[1-9])|(?:36[0-6]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9]))|(?:[+-]?(?:\d{3}[1-9]|\d{2}[1-9]\d|\d{1}[1-9]\d{2}|[1-9]\d{3})|[+]?0000)(?:(?:-(?:(?:1[02]|0[13578])(?:-(?:3[01]|[12]\d|0[1-9]))?|(?:11|0[469])(?:-(?:30|[12]\d|0[1-9]))?|(?:W(?:5[0-3]|[1-4]\d|0[1-9]))(?:-(?:[1-7]))?))|(?:(?:1[02]|0[13578])(?:3[01]|[12]\d|0[1-9])|(?:11|0[469])(?:30|[12]\d|0[1-9])|(?:W(?:5[0-3]|[1-4]\d|0[1-9]))(?:[1-7])?))?)
> ```
> <details>
> <summary>Checker link</summary>
> https://regex101.com/r/SanBDm/1
> </details>

> ### PCRE2
> ```regex
>
> ```
> <details>
> <summary>Checker link</summary>
> 
> </details>

#### Accept format 
| Years only  | Calendar dates                         | Week dates                                          | Ordinal dates           |
|-------------|----------------------------------------|-----------------------------------------------------|-------------------------|
| `YYYY`      | `YYYY-MM-DD`, `YYYY-MM`, `YYYYMMDD`    | `YYYY-Www-D`, `YYYYWwwD`, `YYYY-Www`, `YYYYWww`     | `YYYY-DDD`, `YYYYDDD`   |
| `±YYYY`     | `±YYYY-MM-DD`, `±YYYY-MM`, `±YYYYMMDD` | `±YYYY-Www-D`, `±YYYYWwwD`, `±YYYY-Www`, `±YYYYWww` | `±YYYY-DDD`, `±YYYYDDD` |

> [!Caution]
> `-0000` is not accepted. The years 2 BC, 1 BC, and 1 AD correspond to `-0001`, `(+)0000`, and `(+)0001` respectively.

#### Reference(s)
https://en.wikipedia.org/wiki/ISO_8601#Dates

---

## Times

> ### Python
> ```regex
> (?P<iso8601_times>T?(?:(?:(?:2[0-3]|[01]\d):(?:[0-5]\d):(?:[0-5]\d)(?:[\.,]\d+)?|(?:2[0-3]|[01]\d):(?:[0-5]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?::(?:[0-5]\d))?)?|(?:(?:2[0-3]|[01]\d)(?:[0-5]\d)(?:[0-5]\d)(?:[\.,]\d+)?|(?:2[0-3]|[01]\d)(?:[0-5]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?:[0-5]\d)?)?|(?:(?:2[0-3]|[01]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?::?(?:[0-5]\d))?)?))
> ```
> <details>
> <summary>Checker link</summary>
> https://regex101.com/r/RmsFlQ/2
> </details>

> ### PCRE2
> ```regex
>
> ```
> <details>
> <summary>Checker link</summary>
> 
> </details>

#### Accept format
<table>
    <thead>
        <tr>
            <th colspan="4">Expanded format</th>
        </tr>
        <tr>
            <th>T&lt;times&gt;</th>
            <th>T&lt;times&gt;Z</th>
            <th colspan="2">T&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>Thh:mm:ss</code>, <br/><code>Thh:mm:ss.sss</code>, <code>Thh:mm:ss,sss</code></td>
            <td><code>Thh:mm:ssZ</code>, <br/><code>Thh:mm:ss.sssZ</code>, <code>Thh:mm:ss,sssZ</code></td>
            <td><code>Thh:mm:ss±hh</code>, <br/><code>Thh:mm:ss.sss±hh</code>, <code>Thh:mm:ss,sss±hh</code></td>
            <td><code>Thh:mm:ss±hh:mm</code>, <br/><code>Thh:mm:ss.sss±hh:mm</code>, <code>Thh:mm:ss,sss±hh:mm</code></td>
        </tr>
        <tr>
            <td><code>Thh:mm</code>, <br/><code>Thh:mm.mmm</code>, <code>Thh:mm,mmm</code></td>
            <td><code>Thh:mmZ</code>, <br/><code>Thh:mm.mmmZ</code>, <code>Thh:mm,mmmZ</code></td>
            <td><code>Thh:mm±hh</code>, <br/><code>Thh:mm.mmm±hh</code>, <code>Thh:mm,mmm±hh</code></td>
            <td><code>Thh:mm±hh:mm</code>, <br/><code>Thh:mm.mmm±hh:mm</code>, <code>Thh:mm,mmm±hh:mm</code></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td><code>Thh±hh:mm</code>, <br/><code>Thh.hhh±hh:mm</code>, <code>Thh,hhh±hh:mm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th>&lt;times&gt;</th>
            <th>&lt;times&gt;Z</th>
            <th colspan="2">&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>hh:mm:ss</code>, <br/><code>hh:mm:ss.sss</code>, <code>hh:mm:ss,sss</code></td>
            <td><code>hh:mm:ssZ</code>, <br/><code>hh:mm:ss.sssZ</code>, <code>hh:mm:ss,sssZ</code></td>
            <td><code>hh:mm:ss±hh</code>, <br/><code>hh:mm:ss.sss±hh</code>, <code>hh:mm:ss,sss±hh</code></td>
            <td><code>hh:mm:ss±hh:mm</code>, <br/><code>hh:mm:ss.sss±hh:mm</code>, <code>hh:mm:ss,sss±hh:mm</code></td>
        </tr>
        <tr>
            <td><code>hh:mm</code>, <br/><code>hh:mm.mmm</code>, <code>hh:mm,mmm</code></td>
            <td><code>hh:mmZ</code>, <br/><code>hh:mm.mmmZ</code>, <code>hh:mm,mmmZ</code></td>
            <td><code>hh:mm±hh</code>, <br/><code>hh:mm.mmm±hh</code>, <code>hh:mm,mmm±hh</code></td>
            <td><code>hh:mm±hh:mm</code>, <br/><code>hh:mm.mmm±hh:mm</code>, <code>hh:mm,mmm±hh:mm</code></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td><code>hh±hh:mm</code>, <br/><code>hh.hhh±hh:mm</code>, <code>hh,hhh±hh:mm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th colspan="4">Basic format</th>
        </tr>
        <tr>
            <th>T&lt;times&gt;</th>
            <th>T&lt;times&gt;Z</th>
            <th colspan="2">T&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>Thhmmss</code>, <br/><code>Thhmmss.sss</code>, <code>Thhmmss,sss</code></td>
            <td><code>ThhmmssZ</code>, <br/><code>Thhmmss.sssZ</code>, <code>Thhmmss,sssZ</code></td>
            <td><code>Thhmmss±hh</code>, <br/><code>Thhmmss.sss±hh</code>, <code>Thhmmss,sss±hh</code></td>
            <td><code>Thhmmss±hhmm</code>, <br/><code>Thhmmss.sss±hh:mm</code>, <code>Thhmmss,sss±hhmm</code></td>
        </tr>
        <tr>
            <td><code>Thhmm</code>, <br/><code>Thhmm.mmm</code>, <code>Thhmm,mmm</code></td>
            <td><code>ThhmmZ</code>, <br/><code>Thhmm.mmmZ</code>, <code>Thhmm,mmmZ</code></td>
            <td><code>Thhmm±hh</code>, <br/><code>Thhmm.mmm±hh</code>, <code>Thhmm,mmm±hh</code></td>
            <td><code>Thhmm±hh:mm</code>, <br/><code>Thhmm.mmm±hhmm</code>, <code>Thhmm,mmm±hhmm</code></td>
        </tr>
        <tr>
            <td><code>Thh</code>, <code>Thh.hhh</code>, <code>Thh,hhh</code></td>
            <td><code>ThhZ</code>, <code>Thh.hhhZ</code>, <code>Thh,hhhZ</code></td>
            <td><code>Thh±hh</code>, <br/><code>Thh.hhh±hh</code>, <code>Thh,hhh±hh</code></td>
            <td><code>Thh±hhmm</code>, <br/><code>Thh.hhh±hhmm</code>, <code>Thh,hhh±hhmm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th>&lt;times&gt;</th>
            <th>&lt;times&gt;Z</th>
            <th colspan="2">&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>hhmmss</code>, <br/><code>hhmmss.sss</code>, <code>hhmmss,sss</code></td>
            <td><code>hhmmssZ</code>, <br/><code>hhmmss.sssZ</code>, <code>hhmmss,sssZ</code></td>
            <td><code>hhmmss±hh</code>, <br/><code>hhmmss.sss±hh</code>, <code>hhmmss,sss±hh</code></td>
            <td><code>hhmmss±hhmm</code>, <br/><code>hhmmss.sss±hhmm</code>, <code>hhmmss,sss±hhmm</code></td>
        </tr>
        <tr>
            <td><code>hhmm</code>, <br/><code>hhmm.mmm</code>, <code>hhmm,mmm</code></td>
            <td><code>hhmmZ</code>, <br/><code>hhmm.mmmZ</code>, <code>hhmm,mmmZ</code></td>
            <td><code>hhmm±hh</code>, <br/><code>hhmm.mmm±hh</code>, <code>hhmm,mmm±hh</code></td>
            <td><code>hhmm±hhmm</code>, <br/><code>hhmm.mmm±hhmm</code>, <code>hhmm,mmm±hhmm</code></td>
        </tr>
        <tr>
            <td><code>hh</code>, <code>hh.hhh</code>, <code>hh,hhh</code></td>
            <td><code>hhZ</code>, <code>hh.hhhZ</code>, <code>hh,hhhZ</code></td>
            <td><code>hh±hh</code>, <br/><code>hh.hhh±hh</code>, <code>hh,hhh±hh</code></td>
            <td><code>hh±hhmm</code>, <br/><code>hh.hhh±hhmm</code>, <code>hh,hhh±hhmm</code></td>
        </tr>
    </tbody>
</table>

> [!Caution]
> Not accpet UTC timezone `-00:00` and `-00` such as `Thh:mm:ss-00:00`, `Thh:mm.mmm-00`, etc.

#### Reference(s)
https://en.wikipedia.org/wiki/ISO_8601#Times

## Datetimes

> ### Python
> ```regex
> (?P<iso8601_datetimes>(?:[+-]?(?:\d{2}(?:0[1235679]|[2468][1235679]|[13579][01345789])|(?:0[1235679]|[2468][1235679]|[13579][01345789])00)-(?:(?:36[0-5]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9])|02(?:-(?:2[0-8]|1\d|0[1-9])))|(?:[+-]?(?:\d{2}(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|[2468][048]|[13579][26])00)|[+]?0000)-(?:(?:36[0-6]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9])|02(?:-(?:2[0-9]|1\d|0[1-9])))|(?:[+-]?(?:\d{3}[1-9]|\d{2}[1-9]\d|\d{1}[1-9]\d{2}|[1-9]\d{3})|[+]?0000)-(?:(?:1[02]|0[13578])(?:-(?:3[01]|[12]\d|0[1-9]))|(?:11|0[469])(?:-(?:30|[12]\d|0[1-9]))|(?:W(?:5[0-3]|[1-4]\d|0[1-9]))(?:-(?:[1-7]))))(?:T(?:(?:(?:2[0-3]|[01]\d):(?:[0-5]\d):(?:[0-5]\d)(?:[\.,]\d+)?|(?:2[0-3]|[01]\d):(?:[0-5]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?::(?:[0-5]\d))?)?|(?:(?:2[0-3]|[01]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?::(?:[0-5]\d))?)?))|(?:[+-]?(?:\d{2}(?:0[1235679]|[2468][1235679]|[13579][01345789])|(?:0[1235679]|[2468][1235679]|[13579][01345789])00)(?:02(?:2[0-8]|1\d|0[1-9])|(?:36[0-5]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9]))|(?:[+-]?(?:\d{2}(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|[2468][048]|[13579][26])00)|[+]?0000)(?:02(?:2[0-9]|1\d|0[1-9])|(?:36[0-6]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9]))|(?:[+-]?(?:\d{3}[1-9]|\d{2}[1-9]\d|\d{1}[1-9]\d{2}|[1-9]\d{3})|[+]?0000)(?:(?:(?:1[02]|0[13578])(?:3[01]|[12]\d|0[1-9])|(?:11|0[469])(?:30|[12]\d|0[1-9])|(?:W(?:5[0-3]|[1-4]\d|0[1-9]))(?:[1-7]))))(?:T?(?:(?:(?:2[0-3]|[01]\d)(?:[0-5]\d)(?:[0-5]\d)(?:[\.,]\d+)?|(?:2[0-3]|[01]\d)(?:[0-5]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?:[0-5]\d)?)?|(?:(?:2[0-3]|[01]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?:[0-5]\d)?)?)))
> ```
> <details>
> <summary>Checker link</summary>
> https://regex101.com/r/1fAV6M/1
> </details>

> ### PCRE2
> ```regex
>
> ```
> <details>
> <summary>Checker link</summary>
> 
> </details>

#### Accept format

<table>
    <thead>
        <tr>
            <th colspan="4">Expanded format</th>
        </tr>
        <tr>
            <th>&lt;calendar dates&gt;T&lt;times&gt;</th>
            <th>&lt;calendar dates&gt;T&lt;times&gt;Z</th>
            <th colspan="2">&lt;calendar dates&gt;T&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>YYYY-MM-DDThh:mm:ss</code>, <br/><code>YYYY-MM-DDThh:mm:ss.sss</code>, <br/><code>YYYY-MM-DDThh:mm:ss,sss</code></td>
            <td><code>YYYY-MM-DDThh:mm:ssZ</code>, <br/><code>YYYY-MM-DDThh:mm:ss.sssZ</code>, <br/><code>YYYY-MM-DDThh:mm:ss,sssZ</code></td>
            <td><code>YYYY-MM-DDThh:mm:ss±hh</code>, <br/><code>YYYY-MM-DDThh:mm:ss.sss±hh</code>, <br/><code>YYYY-MM-DDThh:mm:ss,sss±hh</code></td>
            <td><code>YYYY-MM-DDThh:mm:ss±hh:mm</code>, <br/><code>YYYY-MM-DDThh:mm:ss.sss±hh:mm</code>, <br/><code>YYYY-MM-DDThh:mm:ss,sss±hh:mm</code></td>
        </tr>
        <tr>
            <td><code>YYYY-MM-DDThh:mm</code>, <br/><code>YYYY-MM-DDThh:mm.mmm</code>, <br/><code>YYYY-MM-DDThh:mm,mmm</code></td>
            <td><code>YYYY-MM-DDThh:mmZ</code>, <br/><code>YYYY-MM-DDThh:mm.mmmZ</code>, <br/><code>YYYY-MM-DDThh:mm,mmmZ</code></td>
            <td><code>YYYY-MM-DDThh:mm±hh</code>, <br/><code>YYYY-MM-DDThh:mm.mmm±hh</code>, <br/><code>YYYY-MM-DDThh:mm,mmm±hh</code></td>
            <td><code>YYYY-MM-DDThh:mm±hh:mm</code>, <br/><code>YYYY-MM-DDThh:mm.mmm±hh:mm</code>, <br/><code>YYYY-MM-DDThh:mm,mmm±hh:mm</code></td>
        </tr>
        <tr>
            <td><code>YYYY-MM-DDThh</code>, <br/><code>YYYY-MM-DDThh.hhh</code>, <br/><code>YYYY-MM-DDThh,hhh</code></td>
            <td><code>YYYY-MM-DDThhZ</code>, <br/><code>YYYY-MM-DDThh.hhhZ</code>, <br/><code>YYYY-MM-DDThh,hhhZ</code></td>
            <td><code>YYYY-MM-DDThh±hh</code>, <br/><code>YYYY-MM-DDThh.hhh±hh</code>, <br/><code>YYYY-MM-DDThh,hhh±hh</code></td>
            <td><code>YYYY-MM-DDThh±hh:mm</code>, <br/><code>YYYY-MM-DDThh.hhh±hh:mm</code>, <br/><code>YYYY-MM-DDThh,hhh±hh:mm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th>&lt;week dates&gt;T&lt;times&gt;</th>
            <th>&lt;week dates&gt;T&lt;times&gt;Z</th>
            <th colspan="2">&lt;week dates&gt;T&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>YYYY-Www-DThh:mm:ss</code>, <br/><code>YYYY-Www-DThh:mm:ss.sss</code>, <br/><code>YYYY-Www-DThh:mm:ss,sss</code></td>
            <td><code>YYYY-Www-DThh:mm:ssZ</code>, <br/><code>YYYY-Www-DThh:mm:ss.sssZ</code>, <br/><code>YYYY-Www-DThh:mm:ss,sssZ</code></td>
            <td><code>YYYY-Www-DThh:mm:ss±hh</code>, <br/><code>YYYY-Www-DThh:mm:ss.sss±hh</code>, <br/><code>YYYY-Www-DThh:mm:ss,sss±hh</code></td>
            <td><code>YYYY-Www-DThh:mm:ss±hh:mm</code>, <br/><code>YYYY-Www-DThh:mm:ss.sss±hh:mm</code>, <br/><code>YYYY-Www-DThh:mm:ss,sss±hh:mm</code></td>
        </tr>
        <tr>
            <td><code>YYYY-Www-DThh:mm</code>, <br/><code>YYYY-Www-DThh:mm.mmm</code>, <br/><code>YYYY-Www-DThh:mm,mmm</code></td>
            <td><code>YYYY-Www-DThh:mmZ</code>, <br/><code>YYYY-Www-DThh:mm.mmmZ</code>, <br/><code>YYYY-Www-DThh:mm,mmmZ</code></td>
            <td><code>YYYY-Www-DThh:mm±hh</code>, <br/><code>YYYY-Www-DThh:mm.mmm±hh</code>, <br/><code>YYYY-Www-DThh:mm,mmm±hh</code></td>
            <td><code>YYYY-Www-DThh:mm±hh:mm</code>, <br/><code>YYYY-Www-DThh:mm.mmm±hh:mm</code>, <br/><code>YYYY-Www-DThh:mm,mmm±hh:mm</code></td>
        </tr>
        <tr>
            <td><code>YYYY-Www-DThh</code>, <br/><code>YYYY-Www-DThh.hhh</code>, <br/><code>YYYY-Www-DThh,hhh</code></td>
            <td><code>YYYY-Www-DThhZ</code>, <br/><code>YYYY-Www-DThh.hhhZ</code>, <br/><code>YYYY-Www-DThh,hhhZ</code></td>
            <td><code>YYYY-Www-DThh±hh</code>, <br/><code>YYYY-Www-DThh.hhh±hh</code>, <br/><code>YYYY-Www-DThh,hhh±hh</code></td>
            <td><code>YYYY-Www-DThh±hh:mm</code>, <br/><code>YYYY-Www-DThh.hhh±hh:mm</code>, <br/><code>YYYY-Www-DThh,hhh±hh:mm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th>&lt;ordinal dates&gt;T&lt;times&gt;</th>
            <th>&lt;ordinal dates&gt;T&lt;times&gt;Z</th>
            <th colspan="2">&lt;ordinal dates&gt;T&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>YYYY-DDDThh:mm:ss</code>, <br/><code>YYYY-DDDThh:mm:ss.sss</code>, <br/><code>YYYY-DDDThh:mm:ss,sss</code></td>
            <td><code>YYYY-DDDThh:mm:ssZ</code>, <br/><code>YYYY-DDDThh:mm:ss.sssZ</code>, <br/><code>YYYY-DDDThh:mm:ss,sssZ</code></td>
            <td><code>YYYY-DDDThh:mm:ss±hh</code>, <br/><code>YYYY-DDDThh:mm:ss.sss±hh</code>, <br/><code>YYYY-DDDThh:mm:ss,sss±hh</code></td>
            <td><code>YYYY-DDDThh:mm:ss±hh:mm</code>, <br/><code>YYYY-DDDThh:mm:ss.sss±hh:mm</code>, <br/><code>YYYY-DDDThh:mm:ss,sss±hh:mm</code></td>
        </tr>
        <tr>
            <td><code>YYYY-DDDThh:mm</code>, <br/><code>YYYY-DDDThh:mm.mmm</code>, <br/><code>YYYY-DDDThh:mm,mmm</code></td>
            <td><code>YYYY-DDDThh:mmZ</code>, <br/><code>YYYY-DDDThh:mm.mmmZ</code>, <br/><code>YYYY-DDDThh:mm,mmmZ</code></td>
            <td><code>YYYY-DDDThh:mm±hh</code>, <br/><code>YYYY-DDDThh:mm.mmm±hh</code>, <br/><code>YYYY-DDDThh:mm,mmm±hh</code></td>
            <td><code>YYYY-DDDThh:mm±hh:mm</code>, <br/><code>YYYY-DDDThh:mm.mmm±hh:mm</code>, <br/><code>YYYY-DDDThh:mm,mmm±hh:mm</code></td>
        </tr>
        <tr>
            <td><code>YYYY-DDDThh</code>, <br/><code>YYYY-DDDThh.hhh</code>, <br/><code>YYYY-DDDThh,hhh</code></td>
            <td><code>YYYY-DDDThhZ</code>, <br/><code>YYYY-DDDThh.hhhZ</code>, <br/><code>YYYY-DDDThh,hhhZ</code></td>
            <td><code>YYYY-DDDThh±hh</code>, <br/><code>YYYY-DDDThh.hhh±hh</code>, <br/><code>YYYY-DDDThh,hhh±hh</code></td>
            <td><code>YYYY-DDDThh±hh:mm</code>, <br/><code>YYYY-DDDThh.hhh±hh:mm</code>, <br/><code>YYYY-DDDThh,hhh±hh:mm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th colspan="4">Basic format</th>
        </tr>
        <tr>
            <th>&lt;calendar dates&gt;T&lt;times&gt;</th>
            <th>&lt;calendar dates&gt;T&lt;times&gt;Z</th>
            <th colspan="2">&lt;calendar dates&gt;T&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>YYYYMMDDThhmmss</code>, <br/><code>YYYYMMDDThhmmss.sss</code>, <br/><code>YYYYMMDDThhmmss,sss</code></td>
            <td><code>YYYYMMDDThhmmssZ</code>, <br/><code>YYYYMMDDThhmmss.sssZ</code>, <br/><code>YYYYMMDDThhmmss,sssZ</code></td>
            <td><code>YYYYMMDDThhmmss±hh</code>, <br/><code>YYYYMMDDThhmmss.sss±hh</code>, <br/><code>YYYYMMDDThhmmss,sss±hh</code></td>
            <td><code>YYYYMMDDThhmmss±hhmm</code>, <br/><code>YYYYMMDDThhmmss.sss±hhmm</code>, <br/><code>YYYYMMDDThhmmss,sss±hhmm</code></td>
        </tr>
        <tr>
            <td><code>YYYYMMDDThhmm</code>, <br/><code>YYYYMMDDThhmm.mmm</code>, <br/><code>YYYYMMDDThhmm,mmm</code></td>
            <td><code>YYYYMMDDThhmmZ</code>, <br/><code>YYYYMMDDThhmm.mmmZ</code>, <br/><code>YYYYMMDDThhmm,mmmZ</code></td>
            <td><code>YYYYMMDDThhmm±hh</code>, <br/><code>YYYYMMDDThhmm.mmm±hh</code>, <br/><code>YYYYMMDDThhmm,mmm±hh</code></td>
            <td><code>YYYYMMDDThhmm±hhmm</code>, <br/><code>YYYYMMDDThhmm.mmm±hhmm</code>, <br/><code>YYYYMMDDThhmm,mmm±hhmm</code></td>
        </tr>
        <tr>
            <td><code>YYYYMMDDThh</code>, <br/><code>YYYYMMDDThh.hhh</code>, <br/><code>YYYYMMDDThh,hhh</code></td>
            <td><code>YYYYMMDDThhZ</code>, <br/><code>YYYYMMDDThh.hhhZ</code>, <br/><code>YYYYMMDDThh,hhhZ</code></td>
            <td><code>YYYYMMDDThh±hh</code>, <br/><code>YYYYMMDDThh.hhh±hh</code>, <br/><code>YYYYMMDDThh,hhh±hh</code></td>
            <td><code>YYYYMMDDThh±hhmm</code>, <br/><code>YYYYMMDDThh.hhh±hhmm</code>, <br/><code>YYYYMMDDThh,hhh±hhmm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th>&lt;week dates&gt;T&lt;times&gt;</th>
            <th>&lt;week dates&gt;T&lt;times&gt;Z</th>
            <th colspan="2">&lt;week dates&gt;T&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>YYYYWwwDThhmmss</code>, <br/><code>YYYYWwwDThhmmss.sss</code>, <br/><code>YYYYWwwDThhmmss,sss</code></td>
            <td><code>YYYYWwwDThhmmssZ</code>, <br/><code>YYYYWwwDThhmmss.sssZ</code>, <br/><code>YYYYWwwDThhmmss,sssZ</code></td>
            <td><code>YYYYWwwDThhmmss±hh</code>, <br/><code>YYYYWwwDThhmmss.sss±hh</code>, <br/><code>YYYYWwwDThhmmss,sss±hh</code></td>
            <td><code>YYYYWwwDThhmmss±hhmm</code>, <br/><code>YYYYWwwDThhmmss.sss±hhmm</code>, <br/><code>YYYYWwwDThhmmss,sss±hhmm</code></td>
        </tr>
        <tr>
            <td><code>YYYYWwwDThhmm</code>, <br/><code>YYYYWwwDThhmm.mmm</code>, <br/><code>YYYYWwwDThhmm,mmm</code></td>
            <td><code>YYYYWwwDThhmmZ</code>, <br/><code>YYYYWwwDThhmm.mmmZ</code>, <br/><code>YYYYWwwDThhmm,mmmZ</code></td>
            <td><code>YYYYWwwDThhmm±hh</code>, <br/><code>YYYYWwwDThhmm.mmm±hh</code>, <br/><code>YYYYWwwDThhmm,mmm±hh</code></td>
            <td><code>YYYYWwwDThhmm±hhmm</code>, <br/><code>YYYYWwwDThhmm.mmm±hhmm</code>, <br/><code>YYYYWwwDThhmm,mmm±hhmm</code></td>
        </tr>
        <tr>
            <td><code>YYYYWwwDThh</code>, <br/><code>YYYYWwwDThh.hhh</code>, <br/><code>YYYYWwwDThh,hhh</code></td>
            <td><code>YYYYWwwDThhZ</code>, <br/><code>YYYYWwwDThh.hhhZ</code>, <br/><code>YYYYWwwDThh,hhhZ</code></td>
            <td><code>YYYYWwwDThh±hh</code>, <br/><code>YYYYWwwDThh.hhh±hh</code>, <br/><code>YYYYWwwDThh,hhh±hh</code></td>
            <td><code>YYYYWwwDThh±hhmm</code>, <br/><code>YYYYWwwDThh.hhh±hhmm</code>, <br/><code>YYYYWwwDThh,hhh±hhmm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th>&lt;ordinal dates&gt;T&lt;times&gt;</th>
            <th>&lt;ordinal dates&gt;T&lt;times&gt;Z</th>
            <th colspan="2">&lt;ordinal dates&gt;T&lt;times&gt;&plusmn;&lt;utc timezone&gt;</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>YYYYDDDThhmmss</code>, <br/><code>YYYYDDDThhmmss.sss</code>, <br/><code>YYYYDDDThhmmss,sss</code></td>
            <td><code>YYYYDDDThhmmssZ</code>, <br/><code>YYYYDDDThhmmss.sssZ</code>, <br/><code>YYYYDDDThhmmss,sssZ</code></td>
            <td><code>YYYYDDDThhmmss±hh</code>, <br/><code>YYYYDDDThhmmss.sss±hh</code>, <br/><code>YYYYDDDThhmmss,sss±hh</code></td>
            <td><code>YYYYDDDThhmmss±hhmm</code>, <br/><code>YYYYDDDThhmmss.sss±hhmm</code>, <br/><code>YYYYDDDThhmmss,sss±hhmm</code></td>
        </tr>
        <tr>
            <td><code>YYYYDDDThhmm</code>, <br/><code>YYYYDDDThhmm.mmm</code>, <br/><code>YYYYDDDThhmm,mmm</code></td>
            <td><code>YYYYDDDThhmmZ</code>, <br/><code>YYYYDDDThhmm.mmmZ</code>, <br/><code>YYYYDDDThhmm,mmmZ</code></td>
            <td><code>YYYYDDDThhmm±hh</code>, <br/><code>YYYYDDDThhmm.mmm±hh</code>, <br/><code>YYYYDDDThhmm,mmm±hh</code></td>
            <td><code>YYYYDDDThhmm±hhmm</code>, <br/><code>YYYYDDDThhmm.mmm±hhmm</code>, <br/><code>YYYYDDDThhmm,mmm±hhmm</code></td>
        </tr>
        <tr>
            <td><code>YYYYDDDThh</code>, <br/><code>YYYYDDDThh.hhh</code>, <br/><code>YYYYDDDThh,hhh</code></td>
            <td><code>YYYYDDDThhZ</code>, <br/><code>YYYYDDDThh.hhhZ</code>, <br/><code>YYYYDDDThh,hhhZ</code></td>
            <td><code>YYYYDDDThh±hh</code>, <br/><code>YYYYDDDThh.hhh±hh</code>, <br/><code>YYYYDDDThh,hhh±hh</code></td>
            <td><code>YYYYDDDThh±hhmm</code>, <br/><code>YYYYDDDThh.hhh±hhmm</code>, <br/><code>YYYYDDDThh,hhh±hhmm</code></td>
        </tr>
    </tbody>
</table>

#### Reference(s)
https://en.wikipedia.org/wiki/ISO_8601#Combined_date_and_time_representations
