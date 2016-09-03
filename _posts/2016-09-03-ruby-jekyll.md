---
title: "Ruby jekyll"
---

## jekyll 3.2.1 | Error:  Address already in use - bind(2) for 127.0.0.1:4000

這是要用使 <code>jekyll serve</code> 遇到的問題,
原因是同一個 port 已經被使用了,
但是當前的 terminal 並沒有看到執行中的程序，
沒辦法用 Ctrl-C 的方式關閉,
但是 _config.yml 必須重啟才能夠生效,
所以需要以指令的方式關閉,
方法如下,
首先找出執行中的程序id,
然後用 <code>sudo kill<code> 中止。

```sh
$ lsof -wni tcp:4000

COMMAND  PID USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
ruby2.3 9238 ajua    8u  IPv4 112402      0t0  TCP 127.0.0.1:4000 (LISTEN)

$ sudo kill -9238 PID
```

參考 [tcpserver-error-address-already-in-use-bind2](http://stackoverflow.com/questions/10261477/tcpserver-error-address-already-in-use-bind2)

## Paragraphs

**This is a regular paragraph.** Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus. Aenean eu leo quam. Pellentesque ornare sem lacinia quam venenatis vestibulum.

Links look like [this](#). *Emphasis*. <mark>Marked</mark>. <del>Deleted</del>. <code>Code</code>. <kbd>user-input</kbd>.

## Blockquotes

> **This is a blockquote**. Morbi leo risus, porta ac consectetur ac, vestibulum at eros. Sed posuere consectetur est at lobortis.


## Tables

In Shiori, you don't need to add the Bootstrap `.table` class to `table`. It just works.

<table>
  <thead>
    <tr>
      <th>First Name</th>
      <th>Last Name</th>
      <th>Username</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Elle</td>
      <td>Kasai</td>
      <td><a href="http://twitter.com/ellekasai">@ellekasai</a></td>
    </tr>
  </tbody>
</table>

## Code

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Elle')
#=> prints 'Hi, Elle' to STDOUT.
{% endhighlight %}


## Images

Images have round corners and are responsive by default.

![](http://placehold.it/1200x150)

## That's it!

Continue onto [{{ page.previous.title }}]({{ page.previous.url | prepend:site.baseurl }}) to learn more.
