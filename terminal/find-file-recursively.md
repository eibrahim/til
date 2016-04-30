#find a file recursivel and execlude a folder

On mac and linux, you can search a folder for a file by name and exclude a folder wit

```find . -name "package.json"  -not -path "./node_modules/*"```

This will look for `package.json` in current folder recursively and execlude searching in the node_modules folder.

PS: [Thanks to this SO](http://stackoverflow.com/questions/25188290/exclude-sub-directories-from-find)

