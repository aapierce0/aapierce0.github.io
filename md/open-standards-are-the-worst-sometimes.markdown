# Open Standards are the Worst! (Sometimes)

(Attention grabbing headline: check)

There's a common belief in programming circles that open standards and open-source software will always defeat proprietary solutions, even if it takes an eternity. The success of Microsoft Windows, for example, is just an anomoly. One of these days, an open-source linux distribution will rise in popularity, and overthrow it (and it might just be called Android).

In fact, as I type this, an article titled [Your App Is Not Better than an Open Protocol](http://www.andjosh.com/2015/02/15/using-open-protocols/) is [trending on Hacker News](https://news.ycombinator.com/item?id=9074330). In it, the author argues that open standards like SMS, RSS, and Email compatibility are what transformed services like Twitter, WhatsApp, and GitHub into household names.

But at least with proprietary solutions, you have control over the entire platform. You can rest assured that there aren't any issues caused by poorly implemented software on the other end of the network.

Consider Google Reader: [Its shutdown in 2013](http://googlereader.blogspot.com/2013/07/a-final-farewell.html) delivered a huge blow to the community. Not necessarily because it was a good RSS reader on its own (which it was), but because it became the de facto hub of RSS clients everywhere. Most of the popular RSS readers in use at the time weren't truly RSS readers at all – they were merely *Google Reader clients*. App developers were drawn to Google Reader over pure RSS for a variety of reasons, all of which stem from the fact that RSS is an open – uncontrolled – standard.

## Standards-compliant applications still have to handle non-compliance gracefully

There is no central authority that sanitizes RSS feeds. If a user or your RSS application subscribes to a feed that gives you tag soup, you are expected to be able to handle it in a reasonable way – and that's not always easy. So you can either try to build your own sloppy RSS parser, or rely on someone smarter than you to do it on your behalf. That "someone smarter" happened to be Google Reader for most people. Google is a trusted, well established company, and most people already have a Google account they can use with your app, so it is a good fit.

And since we're talking about Google, consider Gmail: it adds a lot of features that aren't present in any commonly used email standard. Labels, colored stars, and "priority inbox" are all features that were built *on top of* standards like IMAP and POP, but aren't actually a part of any commonly used spec. This makes things difficult for mail client makers who are now expected to go beyond the spec to facilitate Gmail's unique features. It shouldn't come as any surprise that we've already begun to see a [rise](http://www.mailboxapp.com/) of [Gmail clients](http://www.google.com/inbox/) instead of true IMAP Email clients. As gmail pulls away from the herd, it becomes more difficult to build a universal mail client.

Consider the Web: I cannot even fathom how difficult it must be to write a web rendering engine that's capable of taking a hot mess of poorly-formed CMS garbage, and figuring out what the developer was trying to accomplish. It's not enough to simply meet the spec, you almost have to *read the developer's mind* to figure out exactly what they were trying to achieve. We even tried solving this once (sorta) by creating the XHTML standard, where well-formed markup was a requirement. There was just one problem: people didn't use it because adhering to a stricter spec was inconvenient, and it didn't offer enough advantages.

## Updating standards is a long and painful process

Even if you're smart enough to roll your own clever RSS parser, you still have another problem to face: syncing which articles have been "read". If someone wants to read an article on their phone, and have it appear as "read" on their computer, (or vice versa), you get the exciting opportunity to invent your very own proprietary solution. Or, you can go where your customers already are and just become a Google Reader client. As a bonus: the "read" state will be synced across *every other* Google Reader client that your user uses, making it even easier for users to switch to your platform (or away from it, as the case may be).

Wouldn't it be great if the RSS spec was updated with a feature to keep track of this data? The problem is, even if the spec was updated, we would still need to update all the RSS generators, and all the RSS clients. It would be years, if not decades before this new version of RSS had become commonplace enough to eschew support for our current version.

If you don't believe me, consider Email: it faced a similar problem early in its lifetime. POP3 didn't have any way of tracking which messages were read and which ones weren't. In fact, it was partially designed on the assumption that people would download their messages to their mail client, *and expect them to be immediately deleted on the server* so that only one instance of the message exists – just like real mail. IMAP was invented in the 80s, but it seems like it wasn't until the mid 00s that it was safe to assume your mail service of choice supported it.

Consider – once again – the Web: Every time a new feature is considered, we have to use a host of browser prefixes to ensure cross-browser compatibility, and sometimes those browser prefixes stick around for *years* before it's safe to use the standard, W3C-blessed form. The fact that we rely on [enormous tables detailing which browsers support certain features](http://caniuse.com/) should be damning evidence that these "standards" are anything but.

## Standards-compliance comes at the cost of either accessibility or performance

In my opinion, most of the "modern web" is an abuse of the HTML/CSS standard. HTML is a great way to define static documents, perhaps with *minimal* interactivity. It is not a good way to create elaborate interactive applications. Rendering the layout of a complex HTML web page is a computationally expensive process. Flipboard realized this, and decided to move to a strictly `<canvas>` based approach for their latest "2.0" release of their web client. The results are, unsurprisingly, [very fluid](http://engineering.flipboard.com/2015/02/mobile-web/). John Gruber put it a [little more bluntly](http://daringfireball.net/linked/2015/02/10/flipboard-web): "To me, that Flipboard went this route is a scathing condemnation of the DOM/CSS web standards stack."

I believe Flipboard chose the correct solution. The HTML/CSS stack was not designed to handle such complex animations so fluidly. The `<canvas>` element, on the other hand, was designed *specifically* for complex animations that couldn't be efficiently achieved using the DOM. However, there's a fairly vocal crowd opposed to the change, mainly due to accessibility concerns. This isn't a bad reason to be opposed to the change, but everyone seems to be ignoring a pretty substantial issue: we shouldn't be forced to choose between performance and accessibility just to achieve standards-compliance.

Suddenly walled gardens and closed protocols don't seem so bad.



