Rentivo API Docs
========

[Rentivo Manage and Lycan Documentation](https://www.rentivo.com).

This is the public repo for the [Rentivo API documentation](https://www.rentivo.com/docs). It was generated using [Slate](https://github.com/slatedocs/slate).

Developing Docs
---------------------

From within the document run install gem bundler with the lockfile version

```
> gem install bundler -v "$(grep -A 1 "BUNDLED WITH" Gemfile.lock | tail -n 1)"
```

Once installed, you can run the standard

```
bundle install
bundle exec middleman server
```

This will then launch on `localhost:4567`


Testing Locally
-----------------------
You'll need Docker.

From the root of the repo:
```
> docker build .
```

Once you've built your image, make note of the image hash:
```
...
Successfully built abcdef1234
```

And run it, forwarding the port, including the first few characters of the image:
```
> docker run -p 4567:4567 abcde
```

Then just visit http://localhost:4567 in your browser!
