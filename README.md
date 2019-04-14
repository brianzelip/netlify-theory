# netlify-theory

I'm making an explicit administrative decision to use Netlify as the platform for my personal site and related work and writing.

This new type of decision for me is the result of working through zelip.me/talks, see

- [zelip.me changelog #10](https://github.com/brianzelip/zelip.me/blob/master/changelog.md#10-migrate-gh-pages-sub-directory-projects-to-netlify)
- [talks notes](https://github.com/brianzelip/talks/blob/master/talks/notes.md)

The old way was based on leveraging GitHub for everything. They do a great job of seamlessly integrating projects as sub directoris of a central, custom domain-enabled repo.

What's happened over time though, is my GitHub is messy! This is because GitHub is also a place for me to experiment and discover. And because they seamlessly integrate projects as sub directories, I don't have an explicit list of what's published behind my brianzelip.github.io/. I have to go through each repo via the GH interface and look up the status of each project. This is wack and too hands-on.

The approach outlined herein will solve these issues by explicitly planning out and documenting what should be, and what is, published.

## 1. Protocol

## 1.1 Implementing projects as sub directories

For static sites and documents. For collections, like talks.

Plan out what should be in a given project. So for example, what should be available via zelip.me:

- home page
- about
- contact
- social links
- cv
- talks (an index of, as well as the contents of, each talk to share)
- apps (an index of, as well as the contents of 0 or more apps to share)

example sub dir:

talks/

- talk one/
- talk two/
- talk three/

### 1.1.1 Lessons

#### 1.1.1.1 Setting up sub directory project

The main documentation on this seems to be, [Can I deploy multiple repositories in a single site?](https://community.netlify.com/t/common-issue-can-i-deploy-multiple-repositories-in-a-single-site/179?u=brianzelip), from the Netlify support forum.

##### 1.1.1.1.1 Main steps

1. The repo should have a folder in the root with the project name, ie, the talks repo should look like:

```
talks
└── talks
    ├── Making-Saves-Lives.pdf
    ├── azellaz-jamstack
    ├── ictr.pdf
    ├── index.html
    ├── loyola-making-saves-lives.pdf
    ├── making-health
    ├── node-mvc
    ├── notes.md
    └── using-github
```

2. Each asset link should be an absolute path prefixed with a slash and the project folder name, as in the new index.html below:

```html
<!-- old index.html -->
<a href="using-github/">Using Github</a>

<!-- new index.html -->
<a href="/talks/using-github/">Using Github</a>
```

3. Create appropriate rewrites via \_redirects. Read [the docs](https://www.netlify.com/docs/redirects/#rewrites-and-proxying). Test them via [redirect playground](https://play.netlify.com/redirects)

4. Include \_redirects in build! See [my face palm post](https://community.netlify.com/t/error-proxying-to-deploy-multiple-repos-in-single-site/303/4?u=brianzelip) that happened because of not including it in the build.

#### 1.1.1.2 Avoid Netlify's "finicky" redirects - push as little as possible!

Redirects can be "finicky", as a support rep mentioned to me. I've experienced the system not working and thought I did something wrong, only to trigger a new deploy (reboot netlify) and then find it working as expected. I imagine this finicky behavior is similiar to the lag experienced from updating DNS info. It's likely best to push the least often, or else you'll have to reboot quite a bit, and feel like the sky is falling quite a bit too.

## 1.2 Implementing projects as sub domains

For apps

- groceries.zelip.me
-
