# netlify-theory

I'm making an explicit administrative decision to use Netlify as the platform for my personal site and related work and writing.

This new type of decision for me is the result of working through zelip.me/talks, see

- [zelip.me changelog #10](https://github.com/brianzelip/zelip.me/blob/master/changelog.md#10-migrate-gh-pages-sub-directory-projects-to-netlify)
- [talks notes](https://github.com/brianzelip/talks/blob/master/talks/notes.md)

The old way was based on leveraging GitHub for everything. They do a great job of seemlessly integrating projects into a central, custom domain-enabled repo. What's happened over time though, is my GitHub is messy! This is because GitHub is also a place for me to experiment and discover. And because they seamlessly integrate projects as sub directories, I don't have an explicit list of what's published behind my brianzelip.githu.io/. This approach will solve these issues by explicitly planning out and documenting what should be and is published.

## Avoid Netlify's "finicky" redirects - push as little as possible!

Redirects can be "finicky", as a support rep mentioned to me. I've experienced the system not working and thought I did something wrong, only to trigger a new deploy (reboot netlify) and then find it working as expected. I imagine this finicky behavior is similiar to the lag experienced from updating DNS info. It's likely best to push the least often, or else you'll have to reboot quite a bit, and feel like the sky is falling quite a bit too.

## 
