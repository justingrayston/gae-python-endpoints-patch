# gae-python-endpoints-patch
Fix for Content Length error when testing for anything other than a 2xx or 3xx response

If you want to use webtest to test for say a 401 if auth invalid etc you get an
error allong the lines of:

```
AssertionError: Content-Length is different from actual app_iter length (512!=62)
```

Here is a patch version with the patch from [stackoverflow](http://stackoverflow.com/questions/24219654/content-length-error-in-google-cloud-endpoints-testing) relating to the [issue raised](https://code.google.com/p/googleappengine/issues/detail?id=10544)

So until it is patched, just download this as a zip and overwrite the library
in the google_appengine/lib/ directory. Remember after it upgrade to diff and replace,
it hasn't changed for a while, and it was October 2014 when the patch was passed
on. Hopefully it will turn up soon.
