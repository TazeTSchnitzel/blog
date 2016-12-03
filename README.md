What's this?
============

A really, really minimal blogging software written in PHP. It's flat-file, just markdown files.

How do I set it up?
===================

1. Check out the repo somewhere on your server. 
2. Run `composer install`.
3. Optionally, create `posts/blog-description.md`, it'll be put on the front page of your blog.
4. Create some posts in `posts`. They'll be listed descending lexicographically, so name them with the ISO 8601 `YYYY-MM-DD` date prefixed (though you don't *have* to). All post files must end in `.post.md`.
5. Point a web server at `src`, making it serve the static files (`style.css` and `noise.png`), and falling back to the `index.php` script when there's no file with the right name. You can use the nginx configuration in `config/nginx/blog.ajf.me` as a guideline.
6. If you want to have images and stuff, stick them in `media`. There's a symlink of it in `src`, so if your web server is pointed there (as it's supposed to be), doing `![](/media/some-image.jpg)` in your posts will work.

Disqus Integration
------------------

1. In `script.js` change the `disqus` property of `config` to `true`.
2. Register your blog on [Disqus](https://disqus.com) to get a shortname for your forum.
3. Change "EXAMPLE" in `//EXAMPLE.disqus.com/embed.js` to the correct shortname for your blog.