
In this lab, we will explore some ideas in networking using command-line tools on our Linux systems.

The lab is for exploration. The assignment suggests some commands to look at and things to try. To complete the assignment, you&rsquo;ll keep a lab notebook explaining what you did and what you noticed.


# Keeping a lab notebook

As a software engineer, it&rsquo;s a good idea to keep a lab notebook about what you are working on. You can record ideas, things to try, what commands you used, what happened when you tried something, documentation consulted, and so on. This is particularly useful when it takes you a while to figure something out. We&rsquo;re always sure we&rsquo;ll remember some strange command syntax, and then we don&rsquo;t.

Look at the manual page (using the `man` command) for every command discussed here. The man pages are your primary reference. If you look up things online, record your query and what resource you asked in your notebook. (This is also a helpful practice, so you can find things later if you need to.)


## Formatting the notebook

To get you started, the assignment includes a starter file for `lab-notebook.md`, with an outline of the top-level parts of the lab. You can also look at the raw version of this file to see how any of the formatting works.

Your lab notebook will be formatted using Markdown, a plain-text format that lets the computer render it in a nicer visual form. You may have noticed this already on our GitHub assignments: when we use the file `README.md` (the `.md` is for &ldquo;Markdown&rdquo;), it renders nicely on the web interface but you&rsquo;ll see the plain text form if you edit it or look at the file in a text editor.

GitHub&rsquo;s version of Markdown is slightly different than some other applications use. You can find a basic reference to it at [Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

It&rsquo;s also a good idea to record the date and time you add something to your notebook.

Since we&rsquo;re using `git`, when you stop work or take a break, it&rsquo;s a good idea to commit your work in progress.


## The assignment and the notebook

The important thing is this assignment is to record what you do, what you notice, and what questions you have. There aren&rsquo;t really any &ldquo;right answers.&rdquo;  A top grade on this assignment needs more than a simple record of commands executed. Let us know what you are thinking about and discover as you go! That said, you probably don&rsquo;t need to have more than a sentence or short paragraph about any one item, unless you want to go that deep. This is still just an introduction, and many of these areas get quite complex.

The questions in the sections below are prompts for you to think about and to get you started. It is not required to answer them specifically&#x2014;this lab is about your curiosity and exploration, not giving simple responses to them.


# General notes

Many of the commands here require superuser privileges. You can use `sudo` or open a superuser shell, but we&rsquo;ll omit the `sudo` part of any commands here. If you notice anything about what kinds of operations require `sudo` and which ones don&rsquo;t, you might record it in your notebook.

Some parts of the manual pages may get more complex than what we&rsquo;ve covered. Don&rsquo;t worry about that; we&rsquo;re exploring the basics right now. If it seems really complicated (like `tcpdump`!), don&rsquo;t worry about it. Pick a little part that seems interesting, and report in your lab notebook.


# Network configuration

Look at the manual pages for the `ifconfig` and `ip` commands. How can you find your IP address with them? Record your VM&rsquo;s address in your notebook.

You can check to see if your network can reach the outside world with the `ping` command.  Verify that you can ping an outside server, then trying configuring the interface down with `ifconfig` or `ip`. Can you still ping an outside server?

Then use the command to bring your interface back up. (If that doesn&rsquo;t work, you can always restart the VM.)

Look at the options for `ifconfig` and `ip`. Pick one you haven&rsquo;t used for each and try it out. What do you notice or wonder about it?


# Finding other systems

Review the man pages for `host` and `dig`, and try them out on different host names you know.. What is similar about them? What is different?

Do the same with `ping` and `traceroute`. What do you discover by using them?


# Network monitoring

Look briefly at the man pages for `tcpdump` and `wireshark` (don&rsquo;t try to understand everything about them!). Try them out on your system. When you have them running, use another window on your VM to run network software, like a web browser. What do you discover?

These are getting complicated enough that asking the Internet for help in understanding things is fine (and still record it in your notebook!).

Along with this file, you&rsquo;ll find one called `http_packet.bin`. It&rsquo;s a packet capture file for practice examining things in Wireshark without trying to watch the network in real time. HTTP is, of course, the network protocol for the World Wide Web, and we&rsquo;ll be looking at that in detail soon. You can load the file with the `File` menu in Wireshark. (It&rsquo;s from [http on the wireshark wiki](https://gitlab.com/wireshark/wireshark/-/wikis/SampleCaptures#hypertext-transport-protocol-http), which has tons of other packet capture files.)


# Scanning other systems

With all these network tools, it&rsquo;s not surprising that there are tools that scan computers over the network to see what services they are running and to gather other information. One common one is called `nmap`. The man page for it is very long. Take a look at it anyway, especially at the &ldquo;Examples&rdquo; section, which describes the policy on scanning `scanme.nmap.org`. You can scan there a few times a day, scan your own laptop system from your VM, and scan your VM. Be careful about choosing other systems to scan, because many network managers don&rsquo;t like it.

Something to think about (and write about in your notebook): how might an attacker use `nmap`? How might a defender use it?

