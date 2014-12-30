# GNATS メモ

* [NetBSD Problem Reports](http://www.netbsd.org/support/send-pr.html "NetBSD Problem Reports")
* [GNATS Bug Database Summary](http://gnats.netbsd.org/summary/ "GNATS Bug Database Summary")

メール宛先 gnats-bugs@NetBSD.org

件名を Re: カテゴリ/番号 と書く

    Subject: Re: kern/5514

# NetBSD のディレクトリだけビルドする

TOOLDIR だけビルドしてあればいい。

    cd /usr/src
    ./build.sh tools

そのあとたとえば dd をビルドする場合はこうする。

    cd /usr/src/bin/dd
    /usr/tools/bin/nbmake

こんだけ

## TOOLDIR

以下のように build.sh で -T した場合は

    ./build.sh -O ../obj -T ../tools tools

ビルド時に TOOLDIR を指定しておくべし。

    cd /usr/src/bin/dd
    /usr/tools/bin/nbmake TOOLDIR=/usr/tools
