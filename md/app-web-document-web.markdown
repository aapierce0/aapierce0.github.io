# The App-Web and the Document-Web

I'm not the first person to say this, but the HTML/CSS stack is simply dreadful for developing modern applications. The web was designed primarily for read-only documents, not interactive applications. People have built empires on what is basically an interwoven series of overcomplicated Microsoft Word documents. In fact, it's gotten so bad, that Palm thought it would be a good idea to build an entire [smartphone platform](http://www.hpwebos.com/us/) on top of it, and even though that never took off, Mozilla decided that they were going to take a [crack at it too](https://www.mozilla.org/en-US/firefox/os/).

Trying to build apps that are fluid, responsive, and engaging by mutating an XML tree is bonkers. There have been countless frameworks created just to get *around* this issue of mutating the DOM directly.

But that's not to say that HTML/CSS is entirely bad. In fact it's still great at solving the problem that it was originally designed to solve – presenting static pages of information in a sensible format. It's still a great format for news articles, blog posts, and other text-based content. In fact, I almost wish someone would build a document-editing application that saves its data as HTML under the hood, instead of .doc or .pdf.

There really needs to be a better solution for these app-based websites, so they don't have to abuse a system designed for static documents.

Flipboard recently launched their new "2.0" version of their web interface for mobile. They threw out the DOM-manipulation version of their site, and replaced it with a javascrpt-powered `<canvas>` application. As it turns out, this approach is *far* more responsive, and actually runs at a smooth 60fps.