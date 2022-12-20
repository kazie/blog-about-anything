---
title: Date & time bugs, strikes again. 😱
published: true
---

## Foreword

You may have already heard it about me.
But I am someone who really have grown battle-worn from different times of bugs, originating around date-times.

Serialisation, the whole civil part about [`timezones`](https://en.wikipedia.org/wiki/Time_zone),
and sometimes even the fabric of time itself, always somehow seem to put a dent to my overall happiness.

Some day, I hope my talk that I am building around it may be spread and known - just to minimize the amount of these kinds of bugs that I really can live without.

## Just a "normal" weekend.

> What do you like to do on weekends?

I guess most of us want to have a good time, and recharge our batteries, and that's what I was set to do.

On Sunday morning, I was going to see a ["raibu" (ライブ)](https://en.wiktionary.org/wiki/%E3%83%A9%E3%82%A4%E3%83%96), a Japanese live show starring some live streamers from a franchise I really like.

![](./img/kf1st.jpg)

It was their first live event, and I was really excited and happy - although I knew that I had to jump through a few hoops in order to see this show.
Because _of course_ the show itself is behind both a <u>paywall</u>, and is <u>region locked</u>.
And don't get me wrong, I have nothing against things being monetised - although it adds extra complexity for someone like me - a total foreigner.

### Region Locking 🕵️

One of the things I did mention, was the whole thing about _region locking_.

This is a well known problem, and has two well known solutions.

1) Move your arse to wherever you need to be.
2) Somehow pretend that you have moved your arse to wherever you need to be.

And when it comes to internet traffic, one could even route their traffic in such a way that the source/origin is in said countries.

One such tool is [`Tor`](https://en.wikipedia.org/wiki/Tor_(network)), which is used both for anonymity online, and can be a great tool to circumvent censorship and oppression.
But it may not be perfect for throughput, and if I want to watch a live-stream with video and sound - I chose to take another approach.

The other tool I am thinking of is `VPN`, which encrypts your traffic and exits from specific, often paid servers around the world.
These ones may be blocked though by streaming services, and I think many big operators are working around it by playing some kind of cat and mouse game. 🐭💨🐱

And when it comes to __VPN__, you can probably seen endless commercials from social media about some services, be it _fast_ or _north_ or some other kind of naming, they most have the same kind of business strategies.
Long term subscriptions, and huge deals, making you commit for them. One has to subscribe with an email address or other personal information, and probably gather and sell it themselves, since if you're using their service, they could just as well be as bad as they are trying to make your ISP out to be.

Although there is a Swedish company called [Mullvad](https://mullvad.net/), that has their code open-source (thus making it easy for me to guess that it WILL work on LINUX), and have policies that speak to me.
No marketing or campaigning, just want to deliver a good service, which __could__ be anonymous. Although I hae heard that they do not play the cat-and-mouse game, so services like Netflix may have blocked their addresses.

### Buying tickets

> So, you thought it would be __easy__ buying some tickets for a live that you wanted to watch?  
> _Think again!_

So, the live show was on the television channel of [TV Asahi (テレビ朝日)](https://en.wikipedia.org/wiki/TV_Asahi). And as they're somewhat modern enough, one would guess that the show I wanted to watch would simply have a "buy" button maybe?

No, that's silly! A __buy__ button? For the __specific thing you want to watch__? Who would design a system like that!

Here you buy _token currencies_, or as we sometimes call it jokingly in Swedish [smurfbär](https://www.aftonbladet.se/nyheter/a/J1lvwP/barnens-ipad-spel-kostade-50-000-kr),
as there was early many parents that noticed their wallets getting emptied by their children playing games on their early Apple devices.

So, to buy my live show, I need to spend `580` "coins", and in order to buy said amount of coins. I can buy the exact amount of needed coins right? ... Well, sorta?

![](./img/shop.png)

In order to acquire `580` coins exactly, I need to buy:

- 250 coins _monthly plan(月額チャージ)_
- 300 coins
- 30 coins

By buying the monthly plan, I saved ¥550 💹, but I had to make sure that I cancel the monthly subscription.

_Gee_, one need to do **math** in order to save money, by not buying an excessive amount of coins, as well as understand things in order to cancel a subscription I didn't want.

> I needed to convert my Swedish Money `SEK` to Japanese ones `YEN` in order to buy pretend tokens 🪙, in three separate transactions, in order to buy an online ticket. 🤦

### Time of the Live

It was Sunday, I woke up, happy and excited for the  2 hours live show.

I used my VPN, which also was needed to buy my ticket, and came to a page where there was a live chat with other excited, although overwhelmingly Japanese audience.

The clock was ticking down to the show, and I saw the Japanese people starting to chat about sudden background music (`BGM`).

>  _Huh? There is no pre-video or BGM?_

I was thinking to myself, but I kept  waiting, and waiting.
And I see as I realise that the show has __started__, but __I__ could see nothing - just the live chat and excited people social media!!

#### Pain

> Can it be that my Mullvad is blocked?

In panic I tried to buy one of those horrible, shitty VPN's, to no avail. Of course their code doesn't work well on _LINUX_.

As a backup I tried my phone, since installing their `app` is easier, although it was still painful to get it to work - I got to the page, and same, nothing, __there is no video__.

What can I say, I was kind of overwhelmed with distress and emotions. Why didn't it work? I could __buy__ the service, but I cannot __watch__ it, what a load of _B\*llsh\*t_!! 😭

But maybe, since it has a live archive until the 9'th of January, I may find a solution somehow - but now my day was ruined, and I did not experience the __live__ part of the live-event.

### What was wrong?

👆 Well, remember the title of this blog-post up above? 👆

> Date & time bugs, strikes again. 😱

Yeah, it was a localization bug that had struck me...

Apparently the Japanese web-code was checking what _time_ it was. This by extracting the __local__ date and time, and with this information it decided:

> > Oh, you're early to the event, this event starts at `18:30` but it is currently `10:30`, no need to load the video platform for this video yet!

So I got to try that if I set the `tz` to `Asia/Tokyo`, on my computer (or Smartphone), I would have been able to watch it live, as this fix was still required to watch the archive afterwards.

Here I am today. I got __burned__ by yet another date-time bug, and this time it gave me personal distress and some temporary emotional damage.
But I am thus also a bit wiser.
I swear, that I will never stop my fight to help and educate and spread the word of these problems.

But at least my weekend didn't get ruined, as I did get to see the show, and it was just as well worth all of this wild ride.
As I did get to watch the event, before it is maybe lost through the sands of time.
