#Handle "Not Authorized" Errors

* First generate a "not authorize route" `ember g route notauth`
* Edit `notauth.hbs` and add some content e.g. "You are not authorized to view this page"
* In your application route, handle a 403 error by replacing the current route with the `notauth` route:

```
  actions: {
    error: function(error /*, t*/) {
      if (error) {
        if (error.status === 403) {
          return this.replaceWith('notauth');
        }
      }
    },
```

Obviously, this only works if your API is sending back a status code of 403 for permission-related errors.


