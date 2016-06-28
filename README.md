# hapi-rate-limit

This limits access to a given route three ways

userLimit: number of total requests a user can make per period
pathLimit: number of total request any user can make on a given path per period
userTimeout: length of period in seconds for userLimit
pathTimeout: length of period in seconds for pathLimit

Default userLimit is 300 requests in 10 minutes
Default pathLimit is 10 requests in 1 minute

both timeouts default to 10 minutes

Add this to route config to override path limit for that route:

```javascript
  plugins: {
    'hapi-rate-limit': {
      pathLimit: 2,
      pathTimeout: 60000 // 1 minute
    }
  }
```

You can disable the `userLimit` or `pathLimit` for any given path with a
route config like this:

```javascript
  plugins: {
    'hapi-rate-limt': {
      pathLimit: false,
      userLimit: false
    }
  }
```
