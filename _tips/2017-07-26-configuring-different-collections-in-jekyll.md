---
layout:     article
title:      Configuring collections in Jekyll
date:       2017-07-26 15:49:27
author:     Fernando Fernandes
summary:    
categories: 
thumbnail:  check-square-o
tags:
 - article
 - jekyll
 - configuring
---

## Expanding the possibilities

The [Jekyll][1] blog engine is amazing in its purpose of building and helping us to keep updated our posts. But sometimes we need something more customized to meet our necessities, right? Yeah, I know and that is the reason why we thought in writing this post. 

While configuring this blog we faced this little stone in our path. We simply were able to derive our default directory structure to include our articles folder and better organize those things.

Now that the problem was solved we want to <em>share</em> it hoping that it could become useful to somebody.

### The problem

Jekyll comes by default ready to deal with pages named <em>posts</em>, but fortunately it's possible to expand this configuration to accomodate other types of content. This brings us the opportunity of well organize our content in groups.  

That type of content (that share a common look, structure and purpose) are called <em>collections</em> by the Jekyll engine. Just adding a new folder prefixed by an underscore won't turn its content into a <em>collection</em>. 

It could be easy like that don't you think? by the way that was my first thought. Ok, but what happens when you do that? The engine will solely ignore the fact you have [Markdown][3] pages in the folder and will make a raw copy of the files to the build destination folder. No Markdown processing for you, at all.

### Making the trick

In order to make the Jekyll engine see our new folder as a collection of markdown pages folder is to configure it in a collections section in the <code>_config.yml</code> file as ilustrated in the snippet below:

```
...
collections:
- receipts
- bills
... 
```

This will make the engine treat our <code>_receipts</code> and <code>_bills</code> as repositories of pages written using [Markdown][3] syntax. This causes the pages to be parsed, built and transferred to the destination folder after the  processing.

**_Attention! DO NOT USE_** the <code>include</code> section of the <code>_config.yml</code>. It will only make the engine copy the folders content without any [Markdown][3] processing. That's not what we're looking for.

That's it! Now, since Jekyll doesn't update the configuration data even with the `--watch` flag set, we just have to re-run the server and check the new behavior.

Would this worth a share? Thank you!


[1]: http://jekyllrb.com
[2]: https://stackoverflow.com/questions/26684279/how-to-add-multiple-contents-in-a-custom-collection-folder-in-jekyll-for-github
[3]: https://daringfireball.net/projects/markdown/