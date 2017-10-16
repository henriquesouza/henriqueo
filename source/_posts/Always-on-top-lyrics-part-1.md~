---
title: 'Always on top lyrics - part 1'
date: 2017-08-11 15:53:48
tags: toply, desktop lyrics displayer, python, gtk, open source, transformers, webextensions
---

TL;DR: [https://github.com/henriquesouza/toply](https://github.com/henriquesouza/toply)

If I had to choose one last thing in life, it'd be music. Power metal, more precisely. It is so motivating and energizing, singing boosts my mood to ridiculously higher levels. But there's a problem: I don't always know the lyrics.

Being aware of that inevitable fact, I decided to ask the internet whether there was any solution addressing to my small question. I honestly found some really interesting stuff, many of which would search for the lyrics in a specific source (something that fails in at least 30% of the cases, even more if you listen to some underground artists), and secondly add closed captions to the YouTube video or a tray to my taskbar. None of them were able to maintain a floating pane over my other applications - I'd needed to either open a window or a species of tab, although all I wanted was to know the upcoming piece of lyrics. Just that.

## K, we now have two questions
How to be sure that **more** lyrics are found (no magic available) and how to keep it over all apps without bothering me and my experience.

First of all, I checked of what those lyrics websites have in common.
1. They're mostly old;
2. They use _`<br />`_ or _`<p>`_ tags to break lines.

In case the question **"why don't you use a lyrics API from the thousands of existent lyrics sites?"** popped in your mind, here's my reply: as far as I know, you can't get the entire content from those providers. Even if you pay for it, there's a limited number of requets (e.g.: $ 200 for 1000 requests :thinking:) you can make per certain period of time. I wanted something to be freely used by people; I don't want every user to be asked to sign up to some API or something binding with a proprietary provider.

## How are the lyrics being "fetched"?
Have you heard of DuckDuckGo? It's a Google rival that promises not tracking its users. There's a lot to be improved when it comes to search results, but they have lots of features that are worth [taking a look](https://duckduckgo.com/about). Just like Google, they've developed a syntax that may bring you more or less accurated results, depending on what you submit as a query. In their syntax page you can check all of them. Google offerers(ed?) you a "I'm feeling lucky" button that would take you to the first result found, but only if you went to their homepage (at google.com). DuckDuckGo offers the exact same thing, but instead of clicking a button, you can add a space + a backslash ( **&#92;**) or a space + a exclamation mark ( **!**) to your queries and be led to the very best result they were able to find with that entry. :smiley:

Eureka! That's it! Now all we have to do is throw the song's info into a search, get the HTML of the page that is most likely to have the lyrics and boom! Always on top lyrics!

Then there it comes the tough part: how the hell am I going to know what is the text and what is not? Oh! Wait! We've already talked about that some paragraphs above: those sites are all kind of old (no fancy JS content placement) and basically use the same tags to break lines. From here, I spent a long time trying to figure out an algorithm that would be able to tell me where it would begin and where it would end. To be honest, only recently I saw that I could have used some of the Firefox's Read View code, due to the similarity between both core ideas (getting the main text of a page). It'd be quite useful at the beginning.

> if next_line.find("<br") > 0:

## Media source
After lines and more lines of tests on potential lyrics texts, the time of identifying the song being played currently came. I almost threw my laptop through my window when trying to figure out an non-invasive way of getting windows' titles or media player trays values/meta data. Behold the FLOSS community strikes back (again)! [freedesktop.org](https://freedesktop.org) has a purpose that should've been the standard since the beginning of the it all: integrate technolgy (desktop tech, in this particular case). One its hundreds of utilities is the D-Bus system, that in short, allow apps to talk withing themselves, for example: thanks to that, I'm now able to get the current song being played and all of its meta info, like artist(s), release year, if it's playing or stopped right now, stop it, if I want. All I wrote until now is only able to fetch information from VLC, but with three or four lines I could add Spotify and whatever else.

It can be said that we've solved the issue on _how to get what's playing right now_. We only listen to music in Spotify or in our default media player, right? So that's it. Now all we need is syc... Excuse me? You listen to songs on your browser too? Hm, well observed.

## Browsers are people too
Wait. Not really, but they can give you access to songs too, and that's awesome. It would be better if you had lyrics being showed with browsers as well. Cross-browser solutions are always hard, I know. Luckily WebExtensions are a thing now. If you write something for Firefox, it is going to work on Chrome, Opera and Edge (mostly ¯\\_(ツ)_/¯). It would not need to be anything highly complex. The difference is that now it will need to idenfiy if there's something being played in _that_ tab, and also whether it's a song or not and make a request to a brand-new web service listenning a local port. The application will do the rest of the job once it has the song info (such as title and artist(s)).

## Autobots, sync out!
I don't know about you, but I like to read what's being sang in the moment it's being sang, not in any other moment. Jokes apart, it seems crucial to have a mechanism specially created to align the timing of the songs with the lyrics we got paragraphs ago. There's a file format called .lrc. It's the same as film subtitles, but for songs. It follows "[0:00,00] Perferendis adipisci nobis" format and can be imported to other lyrics utilities. That's probably the most advanced place I have got to - having two threads to both show a small window with a verses list and monitor the movement of the cursor between the lines of that list -. The basic is already working, though you can't edit lyrics pre-synched (just synch new ones).

## There is more
It's been fun to work on that project. I had never worked with Python and felt quite welcome by the language and its endless resources. In case you're wondering what you need to run what exists until now, you only need Python 3.x and GTK 3.x in your machine to test this premature (and promising hehe) lyrics displayer (no installer avaliable yet). This article is going to gain a second part once I find ~~peace~~ inspiration to write it. I still want to talk about other important features that will make it work and about the experience I'm having by trying new tricks out.

## Always on top lyrics
That's what **toply** means (top lyrics, to be more precise). I thought it was a catchy name and also quite strong at representing the idea behind this application. I hope you liked it and also hope that there isn't some big player using the name :sweat_smile:.

---

I'm looking forward to know your opinions on toply and on the article you just read. Thank you for staying until the end, by the way. In case you want to share some of your thoughts, hit me at hey@henriqueo.com.br or at [Mastodon](http://mstdn.io/@henriqueo).
