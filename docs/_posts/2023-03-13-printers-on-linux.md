---
title: Printers on Linux? It's more likely than you think 🐧🖨️
published: true
---

## Preamble

You have probably seen them before. Large machines in the office that prints out papers with stuff on them.
And yeah, we do live in the 21st century - and we still have the need of printers - I know, I am shocked as well.

These machines usually [don't bring joy](https://theoatmeal.com/comics/printers) to anyone who dares to touch them.
But still we have to use them every once in a while. 

Anyhow, on to the real part of this post.

## Printing on Linux 📄

> It just doesn't want to work!

Yeah, there I said what many are saying - printers won't magically work on Linux.
Maybe if you have something like [Ubuntu](https://ubuntu.com/), [Debian](https://www.debian.org/) or [Fedora](https://getfedora.org/) (to name a few) with some default installed packages for your desktop - sure that does make things _a lot easier_.

But here I was, with my [Arch Linux](https://archlinux.org/), in deep metaphysical pain.

### Read the docs ☝️🤓

> Well, you can just hope that everything falls in place if you [read the docs](https://wiki.archlinux.org/title/Category:Printers), but if you're me, it won't help you right off.


### TL;DR 🥷

> Here is a small guide for people, at least employed in the same company as me with an _Arch Linux_ distribution to allow printing of documents in the office.

1. Install [`CUPS`](https://wiki.archlinux.org/title/CUPS)
2. Enable/Start [`CUPS`](https://wiki.archlinux.org/title/CUPS) (and/or the socket-service)
3. Install [`cups-filters`](https://wiki.linuxfoundation.org/openprinting/cups-filters)
4. Install [Canon Drivers `aur/canon-cque`](https://aur.archlinux.org/packages/canon-cque)
5. Install [`ghostscript`](https://www.ghostscript.com/)
6. Install [`system-config-printer`](https://github.com/OpenPrinting/system-config-printer) for easier management and adding things like printers.
7. (optional?) Install [`foomatic-db*`]() drivers, open source drivers.

*Damn* that's a lot of things to install, and maybe some of them are not even necessary - but that's what it took for me to make it work!

#### Setup the printer
I set it up using the `system-config-printer` program, elevated as `sudo` - since hey I don't know if all i need is the `lp` group or whatever ...

First, you want to use the big and obvious _Add_ button
![](./img/print1.png)

Then at the Magello office, find the damn printer while logged into the office network, at `192.168.1.197`.
![](./img/print2.png)

Then after pressing a lot of next buttons, you should have gotten the correct drivers, maybe the `PXL` driver even and have a printer ready for printing - test by pressing `Print Test Page`.
![](./img/print3.png)

#### When everything fails...
Read the cups error log, at `/var/log/cups/error_log`. It could help you, as it was through this I finally learned to install ghostscript:

```
D [10/Mar/2023:13:18:33 +0100] [Job 4] ================================================
D [10/Mar/2023:13:18:33 +0100] [Job 4] File: <STDIN>
D [10/Mar/2023:13:18:33 +0100] [Job 4] ================================================
D [10/Mar/2023:13:18:33 +0100] [Job 4] Filetype: PDF
D [10/Mar/2023:13:18:33 +0100] [Job 4] Storing temporary files in /var/spool/cups/tmp
D [10/Mar/2023:13:18:33 +0100] [Job 4] PID 231957 (/usr/lib/cups/filter/pdftopdf) exited with no errors.
D [10/Mar/2023:13:18:33 +0100] [Job 4] sh: line 1: gs: command not found
D [10/Mar/2023:13:18:33 +0100] [Job 4] Process is dying with \"Unable to determine number of pages, page count: -1
D [10/Mar/2023:13:18:33 +0100] [Job 4] \", exit stat 3
```

Where that `gs` command that was missing, was `ghostscript` which was not installed yet (yeah, what is dependencies anyway).

Sometimes the answer is just obvious, and right in front of me ... but I am too stupid to check the error logs.

## End 🏖️
And that's my short rant for this time. Hope it may help anyone of my co-workers also using Arch Linux to use the printers. 😄
