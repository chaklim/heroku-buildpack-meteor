# Heroku buildpack for meteor

**NOTE** This fork doesn't force you to use Heroku's MongoHQ / MongoLab install (It needs your credit card)
**NOTE** This fork works with Meteor v0.6.4, but has not been tested (and probably won't work) with older versions of Meteor

## Usage

```
% heroku create --stack cedar --buildpack https://github.com/chaklim/heroku-buildpack-meteor.git
```

## Example

Create a sample app with 'meteor'

```
% meteor create --example wordplay
wordplay: created.

To run your new app:
   cd wordplay
   meteor
```

Put it in git.

```
% cd wordplay
% git init
Initialized empty Git repository in /tmp/a/wordplay/.git/
% git add .
% git commit -m "Sample wordplay app!"
```

Create your heroku app

```
% heroku create <yourAppName> --stack cedar --buildpack https://github.com/chaklim/heroku-buildpack-meteor.git
```

Configure your ROOT_URL setting
```
% heroku config:add ROOT_URL=<insert_url_created_above_here>
```

Configure your MONGO_URL setting (use MongoHQ as an example, you may replace it with other MongoDB services)
```
% heroku config:add MONGO_URL=mongodb://<user>:<password>@dharma.mongohq.com:10014/<username>
```

Deploy it

```
% git push heroku master
```

Enjoy!
