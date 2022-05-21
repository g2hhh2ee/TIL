220521

When it goes through that middle server, we need to tell it, where which domains that we actually allow. Otherwise, anyone can kind of throw their images in there, they just loaded. We don't want that. So we have to white-list the domains that we actually want.

=> in `next.config.js`
(configuration file for a server which run in a middle ground.)

```javascript
module.exports = {
  reactStrictMode: true,
  images: {
    domains: ["domain address"],
  },
};
```

like this!

and after you update your config file, of course it is config file, we have to restart server!
