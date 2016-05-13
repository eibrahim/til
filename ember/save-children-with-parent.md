#Save children with parent

If you have a model and you want to save the children when you save the parent.  For example, if you have a Post model that has multiple comments, you can trigger a save on all comments when you save the post with the following:

```
  save(){
    this.get('comments').invoke('save');
    this._super(...arguments);
  }
```



