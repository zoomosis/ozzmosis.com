---
layout: post
title:  Blog hosted on GitHub Pages
date:   2020-07-07 07:07:07 +1000
---
<img src="/img/github-logo.png" width="150" height="150" alt="GitHub logo">

Some months back I'd taken my blog offline, but it's now hosted on [GitHub
Pages](https://pages.github.com/):

<img src="/img/github-pages-settings.png" width="623" height="465" alt="GitHub Pages Settings">

I'd known about their free web hosting but was unaware it was possible (and
common!) to use a CNAME DNS record to map to a GitHub Pages site using a
[custom domain](https://docs.github.com/en/github/working-with-github-pages/configuring-a-custom-domain-for-your-github-pages-site).
For my blog, the important lines in the DNS record for ozzmosis.com were:

```
@ 3600 IN ALIAS zoomosis.github.io.
www 3600 IN CNAME zoomosis.github.io.
```

The ALIAS line allows anyone visiting
[http://ozzmosis.com/](http://ozzmosis.com/) to be redirected to
[http://www.ozmosis.com/](http://www.ozmosis.com/). Because I have "Enforce
HTTPS" enabled on the Settings page for the [GitHub repo of the web
site](https://github.com/zoomosis/ozzmosis.com), this in turn redirects to the
secure site at [https://www.ozzmosis.com/](https://www.ozzmosis.com/). Security
certificates used by HTTPS are automatically generated by GitHub Pages and
issued by [Let's Encrypt](https://letsencrypt.org/).

Many domain registrars also provide [free e-mail
hosting](https://docs.gandi.net/en/gandimail/index.html) for domains registered
with them. Combine this with free web hosting on GitHub Pages means you can
quickly and easily set up a web site and email address for just the cost of a
domain name (approx AU$25/year), with a domain name you control.

The advantage of using your own domain name means it's portable. In the
unlikely event GitHub Pages is discontinued I can host my web site elsewhere
and keep using the same web site address. I can also choose to move my e-mail
hosting elsewhere, keeping the same e-mail address.

I've since learned [Netlify](https://www.netlify.com/) provides free hosting
for web sites with a [https://github.com/](GitHub),
[GitLab](https://about.gitlab.com/) or [Bitbucket](https://bitbucket.org/)
repository, so that may be something to look at in the future.

Also it appears GitLab has its own free version of GitHub Pages, appropriately
named [GitLab Pages](https://docs.gitlab.com/ee/user/project/pages/).

For this blog I'm using [Jekyll](https://jekyllrb.com/) for static page
creation, currently using a modified dark version of the Minima theme.
