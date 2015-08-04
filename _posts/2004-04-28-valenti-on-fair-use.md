---
layout: post
title: Valenti on Fair Use
date: 2004-04-28 11:21
author: jrj
comments: true
categories: [Uncategorized]
---
MPAA's Jack Valenti (of "the VCR is the Boston Strangler" fame) was interviewed by a MIT student regarding fair use law. The result was <a href="http://web.mit.edu/comm-forum/forums/valenti.html" target="_blank">a fascinating look at two opposing viewpoints</a>.
<br />
<br />The most amazing moment was when the kid showed Valenti a simple Perl script that would decrypt and play a DVD. Here's the exchange:
<br />*
<br />[Winstein shows Valenti his “qrpff” DVD descrambler.]
<br />
<br />Winstein: If you type that in, it’ll let you watch movies.
<br />
<br />Jack Valenti: You designed this?
<br />
<br />Winstein: Yes.
<br />
<br />Jack Valenti: Un-fucking-believable.
<br />*
<br />The code (which Winstein didn't actually design-- he adapted it from existing code) was a simple perl script.
<br /><pre>
<br />$_='while(read+STDIN,$_,2048){$a=29;$c=142;if((@a= unx"C*",$_)[20]&amp;48){$h=5;
<br />$_=unxb24,join"",@b=map {xB8,unxb8,chr($_^$a[--$h+84])}@ARGV;s/...$/1$&amp;/;$ d=unxV,xb25,$_;$b=73;$e=256|(ord$b[4])&gt;8^($f=($t=255)&amp;($d&gt;&gt;12^$d&gt;&gt;4^$d^$d/8)) &gt;8^($t&amp;($g=($q=$e&gt;&gt;14&amp;7^$e)^$q*8^$q&lt; &lt;6) )&lt;&lt;9,$_=(map{$_%16or$t^=$c^=($m=(11,10,116,100,1 1,122,20,100)[$_/16%8])&amp;110;
<br />$t^=(72,@z=(64,72,$a ^=12*($_%16-2?0:$m&amp;17)),$b^=$_%64?12:0,@z)[$_%8]}( 16..271))[$_]^(($h&gt;&gt;=8)+=$f+(~$g&amp;$t))for@a[128.. $#a]}print+x"C*",@a}';s/x/pack+/g;eval
<br /></pre>
<br />
<br />I'm sure I'm going to get some sort of cease and desist letter for posting this... but the point I'm trying to make is that this doesn't COPY a dvd, or assist the user in sharing it on the Internet-- it allows the user to PLAY the movie. There's nothing sinister about it.
