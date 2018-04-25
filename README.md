# Harp’s Blog Boilerplate

_This is a boilerplate to use with the _[_Harp Platform_](http://harp.io/)_ and/or the _[_Harp Server_](http://harpjs.com/)_ \(a static web server with built-in pre-processing build with NodeJS\)_

## Index

* [How to use it?](./#how-to-use-it)
  * [On your own computer](./#on-your-own-computer)
  * [On the Harp Platform](./#on-the-harp-platform)
* [Controlling your content](./#controlling-your-content)
* [Adding new posts](./#adding-new-posts)
* [Adding new pages](./#adding-new-pages)
* [Migrating from different platforms](./#migrating-from-different-platforms)
  * [WordPress](./#wordpress)
  * [Tumblr](./#tumblr)
* [TODOs](./#todos)
* [Support](./#support)
* [License](./#license)

## How to use it?

### On your own computer

1. [Install Harp Server](http://harpjs.com/docs/environment/install) on your computer
2. Open your terminal and start a new project:

```text
$ git clone git@github.com:harp-boilerplates/hb-blog.git my-blog
$ cd my-blog
$ harp server -p 9966
```

Go to [http://localhost:9966](http://localhost:9966/) from your browser to see your website.

### On the Harp Platform

1. Login to the [Harp Platform](http://harp.io/)
2. Create a new application
3. Choose **Blog Boilerplate** as your starting point
4. Start your application
5. Open and edit the files in your Dropbox

## Controlling your content

Harp brings you back to the basics of the web. Always keep in mind that your directory structure and file names are your URL paths.

Creating a new page is as simple as creating a new file and writing content in it.

### `public/posts`

This is where your posts and their content live.

### `public/_layout.jade`

The layout of your site, including header, footer and sidebar. External scripts or stylesheets are included in this file. Global elements belong here as well \(i.e.: header, nav, sidebar, etc.\)

### `public/index.jade`

This is the default page when you visit your domain \(i.e.: `http://localhost:9966/`\). Here we build the loop that goes through your posts and shows them in the front page.

### `public/assets/css/app.less`

This is the place where your blog CSS should live.

## Adding new posts

**1**. Create a new file \(`.jade`, `.ejs`, `.html` or `.md`\) in the `public/posts/` directory

```text
$ touch public/posts/kittens.html
```

**2**. Enter your post content in the file you just created:

_public/posts/kittens.html:_

```text
<h1><a href="/posts/kittens">I love kittens!</a></h1>
<p>This is my first post using Harp!</p>
```

**3**. Open `public/posts/_data.json` and add your new post data:

```text
{
  ...                        <-- other blog posts
  "kittens": {               <-- post slug (file name without extension)
    "title": "Cute Kittens"  <-- post title
  }
  ...                        <-- other blog posts
}
```

## Adding new pages

**1**. Create a new file inside the `public` directory:

```text
$ touch public/about.html
```

**2**. Enter the page content in the newly created file

_public/about.html:_

```text
<h1>About me</h1>
<p>I love fotoshapz and taking pictures of foods</p>
```

**3**. Your can now access your page in your browser. I.e.: `http://localhost:9966/about`

## Migrating from a WordPress blog

If you’re planning to move your WordPress site to Harp, I’d recommend cloning it using wget or curl:

This one-line terminal command will create a static replica of **yourwebsite.com** in your computer, it’ll fix all the links to work locally and download all the necessary assets \(images, javascript, css and other files\):

```text
$ wget --recursive --no-clobber --page-requisites --html-extension --convert-links yourwebsite.com
```

## Enabling/Disabling Comments

This blog boilerplate makes it really easy to enable your visitors to leave comments on your blog posts.

Open the `/harp.json` file and look for the disqus section. It should look something like this:

```text
...
"disqus": {
  "enabled": false,
  "shortname": ""
}
...
```

In the disqus configuration there are two configurable keys:

`enabled`: can be `true` or `false`. Make it true to display comments and false to disable them. Make sure the value is not wrapped in quotes like this `"false"`, otherwise it will still show the comments.

`shortname`: this is your shortname assigned by Disqus. [Signup for Disqus](https://disqus.com/admin/signup/) and get your own shortname, then enter it as a string \(with wrapping double quotes\) as the shortname value.

This is what it looks like when it’s enabled:

```text
...
"disqus": {
  "enabled": true,
  "shortname": "jorgepedret"
}
...
```

## Enabling/Disabling Sitemap.xml

Open the `/harp.json` file and look for the sitemap section:

```text
...
"sitemap": {
  "enabled": true,
  "changefreq": "daily"
}
...
```

Change "changefreq" to fit your blog needs. The result will be live in /sitemap.xml

## Support

Please [create an issue](https://github.com/harp-boilerplates/hb-blog/issues) on github’s bug tracker. Feedback and bug reports are greatly appreciated.

## License

MIT



\(this is a test\)

