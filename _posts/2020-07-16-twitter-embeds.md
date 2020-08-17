---
title: Twitter “Embed” Cards While Respecting Privacy
description: A quick demo!
author: hodev
image: https://source.unsplash.com/featured?future
---

We wanted to quote/embed a tweet in our blog, but don't like the idea of pulling in JS or even an iframe from Twitter's servers. So insted, we recreate a tweet card locally, making sure to follow the [Twitter Display Requirements](https://developer.twitter.com/en/developer-terms/display-requirements). Check it out:

```liquid
{% raw %}{% include twitter-card.html
  name="Cassidy James Blaede"
  account="CassidyJames"
  avatar="https://en.gravatar.com/userimage/191535472/070abcd77dbf913d536f48d1bc480071.png?size=200"
  id="1284790188686942208"
  timestamp="2020-07-10"
  contents="Bloc-Editor new way of managing contents and distributable collection of data"
%}{% endraw %}
```

Turns into:

{% include twitter-card.html
  name="Hodev"
  account="Hodev2"
  avatar="https://en.gravatar.com/userimage/191535472/070abcd77dbf913d536f48d1bc480071.png?size=200"
  id="1284790188686942208"
  timestamp="2020-07-10"
  contents="Bloc-Editor new way of managing contents and distributable collection of data"
%}

This is all rendered and styled localy, ensuring we're not hitting Twitter's tracking code just to show some content. It also means quoted tweets will persist, even if removed from Twitter (since it's just local content). It's even light/dark style aware!

It does not (yet) support showing retweets, verified badges, or embedded media. If/when the need arises for those, we can add them, though. Profile images must be manually passed in, as well—ideally included with the regular assets for a post so all assets are staying local to the domain.
