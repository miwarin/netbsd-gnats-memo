# GNATS メモ

* [NetBSD Problem Reports](http://www.netbsd.org/support/send-pr.html "NetBSD Problem Reports")
* [GNATS Bug Database Summary](http://gnats.netbsd.org/summary/ "GNATS Bug Database Summary")
* [Summary of Problem Reports in State &quot;open&quot;](http://gnats.netbsd.org/summary/state/open.html "Summary of Problem Reports in State &quot;open&quot;")

メール宛先 gnats-bugs@NetBSD.org

件名を Re: カテゴリ/番号 と書く

    Subject: Re: kern/5514

# 参考

クロスリファレンス
http://nxr.netbsd.org/

UNIXの仕様
[Text of the Single UNIX Specification, version 3 (= POSIX:2001), 2004 edition](http://www.opengroup.org/onlinepubs/009695399/ "Text of the Single UNIX Specification, version 3 (= POSIX:2001), 2004 edition")

NetBSD そーすリポジトリ

* [NetBSD CVS Repositories](http://cvsweb.netbsd.org/cgi-bin/cvsweb.cgi/ "NetBSD CVS Repositories")

FreeBSD ソースリポジトリ
* [ViewVC Repository Listing](https://svnweb.freebsd.org/ "ViewVC Repository Listing")
* [freebsd/freebsd](https://github.com/freebsd/freebsd "freebsd/freebsd")

# NetBSD のディレクトリだけビルドする

TOOLDIR だけビルドしてあればいい。

    cd /usr/src
    ./build.sh tools

そのあとたとえば dd をビルドする場合はこうする。

    cd /usr/src/bin/dd
    /usr/tools/bin/nbmake

    cd /usr/src/usr.bin/man
    /usr/tools/bin/nbmake-i386


こんだけ

ビルドすると以下のディレクトリに生成される。

    /usr/obj/usr.bin/man/man

## TOOLDIR

以下のように build.sh で -T した場合は

    ./build.sh -O ../obj -T ../tools tools

ビルド時に TOOLDIR を指定しておくべし。

    cd /usr/src/bin/dd
    /usr/tools/bin/nbmake TOOLDIR=/usr/tools
