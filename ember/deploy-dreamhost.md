#Deploy to dreamhost using SSH and rsync


* Install the required plugins
  * `ember install ember-cli-deploy`
  * `ember install ember-cli-deploy-build`
  * `ember install ember-cli-deploy-revision-data`
  * `ember install ember-cli-deploy-display-revisions`
  * `ember install ember-cli-deploy-ssh-index`
  * `ember install ember-cli-deploy-rsync`
* Update config/deploy.js
```
module.exports = function(deployTarget) {
  var ENV = {
    build: {},
    'revision-data': {
      type: 'git-commit'
    },
    'ssh-index': {
      remoteDir: "/home/username/myapp",
      username: "username",
      host: "www.dotnetfactory.com",
      privateKeyFile: "~/.ssh/id_rsa",
      allowOverwrite: true
    },
    rsync: {
      dest: "/home/username/myapp",
      host: "username@myserver.com",
      privateKeyFile: "~/.ssh/id_rsa",
      delete: false
    }
  };

  if (deployTarget === 'development') {
    ENV.build.environment = 'development';
  }

  if (deployTarget === 'staging') {
    ENV.build.environment = 'production';
  }

  if (deployTarget === 'production') {
    ENV.build.environment = 'production';
  }

  return ENV;
};

```
* deploy with `ember deploy production --activate=true`

PS: Thanks to  [http://emberigniter.com/deploy-ember-cli-app-amazon-s3-linux-ssh-rsync/](http://emberigniter.com/deploy-ember-cli-app-amazon-s3-linux-ssh-rsync/)

