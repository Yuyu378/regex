# Regex
Regex

## [ISO8601](https://en.wikipedia.org/wiki/ISO_8601)

### Dates
```regex
(?P<iso8601_dates>[+-]?(?:\d{2}(?:0[1235679]|[2468][1235679]|[13579][01345789])|(?:0[1235679]|[2468][1235679]|[13579][01345789])00)(?:-(?:(?:36[0-5]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9])|02(?:-(?:2[0-8]|1\d|0[1-9]))?)|02(?:2[0-8]|1\d|0[1-9])|(?:36[0-5]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9]))|(?:[+-]?(?:\d{2}(?:0[48]|[2468][048]|[13579][26])|(?:0[48]|[2468][048]|[13579][26])00)|[+]?0000)(?:-(?:(?:36[0-6]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9])|02(?:-(?:2[0-9]|1\d|0[1-9]))?)|02(?:2[0-9]|1\d|0[1-9])|(?:36[0-6]|3[0-5]\d|[12]\d{2}|0[1-9]\d|00[1-9]))|(?:[+-]?(?:\d{3}[1-9]|\d{2}[1-9]\d|\d{1}[1-9]\d{2}|[1-9]\d{3})|[+]?0000)(?:(?:-(?:(?:1[02]|0[13578])(?:-(?:3[01]|[12]\d|0[1-9]))?|(?:11|0[469])(?:-(?:30|[12]\d|0[1-9]))?|(?:W(?:5[0-3]|[1-4]\d|0[1-9]))(?:-(?:[1-7]))?))|(?:(?:1[02]|0[13578])(?:3[01]|[12]\d|0[1-9])|(?:11|0[469])(?:30|[12]\d|0[1-9])|(?:W(?:5[0-3]|[1-4]\d|0[1-9]))(?:[1-7])?))?)
```
#### Accept format 
| Calendar dates                      | Week dates                                      | Ordinal dates         |
|-------------------------------------|-------------------------------------------------|-----------------------|
| `YYYY-MM-DD`, `YYYY-MM`, `YYYYMMDD` | `YYYY-Www-D`, `YYYYWwwD`, `YYYY-Www`, `YYYYWww` | `YYYY-DDD`, `YYYYDDD` |

#### Online Checker
https://regex101.com/r/SanBDm/1

#### Reference(s)
https://en.wikipedia.org/wiki/ISO_8601#Dates

---

### Times

```regex
(?P<time>T?(?:(?:(?:2[0-3]|[01]\d):(?:[0-5]\d):(?:[0-5]\d)(?:[\.,]\d+)?|(?:2[0-3]|[01]\d):(?:[0-5]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?::(?:[0-5]\d))?)?|(?:(?:2[0-3]|[01]\d)(?:[0-5]\d)(?:[0-5]\d)(?:[\.,]\d+)?|(?:2[0-3]|[01]\d)(?:[0-5]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?:[0-5]\d)?)?|(?:(?:2[0-3]|[01]\d)(?:[\.,]\d+)?)(?:Z|(?:[+-](?:2[0-3]|[01][1-9])|[+]00)(?::?(?:[0-5]\d))?)?))
```
#### Accept format
<table>
    <thead>
        <tr>
            <th>T&lt;time&gt;</th>
            <th>T&lt;time&gt;Z</th>
            <th colspan="2">T&lt;time&gt;&plusmn;&lt;utc timezone&gt;</th>
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
            <td><code>Thh</code>, <code>Thh.hhh</code>, <code>Thh,hhh</code></td>
            <td><code>ThhZ</code>, <code>Thh.hhhZ</code>, <code>Thh,hhhZ</code></td>
            <td><code>Thh±hh</code>, <br/><code>Thh.hhh±hh</code>, <code>Thh,hhh±hh</code></td>
            <td><code>Thh±hh:mm</code>, <br/><code>Thh.hhh±hh:mm</code>, <code>Thh,hhh±hh:mm</code></td>
        </tr>
    </tbody>
    <thead>
        <tr>
            <th>&lt;time&gt;</th>
            <th>&lt;time&gt;Z</th>
            <th colspan="2">&lt;time&gt;&plusmn;&lt;utc timezone&gt;</th>
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
            <td><code>hh</code>, <code>hh.hhh</code>, <code>hh,hhh</code></td>
            <td><code>hhZ</code>, <code>hh.hhhZ</code>, <code>hh,hhhZ</code></td>
            <td><code>hh±hh</code>, <br/><code>hh.hhh±hh</code>, <code>hh,hhh±hh</code></td>
            <td><code>hh±hh:mm</code>, <br/><code>hh.hhh±hh:mm</code>, <code>hh,hhh±hh:mm</code></td>
        </tr>
    </tbody>
</table>

> [!Caution]
> Not accpet UTC timezone `-00:00` and `-00` like `Thh:mm:ss-00:00`, `Thh:mm.mmm-00`, etc.

#### Online Checker
https://regex101.com/r/RmsFlQ/2

#### Reference(s)
https://en.wikipedia.org/wiki/ISO_8601#Times

