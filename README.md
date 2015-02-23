Heroku buildpack: Hugo
===

This is a [Heroku buildpack](https://devcenter.heroku.com/articles/buildpacks)
for sites powered by [Hugo](https://github.com/spf13/hugo).
It uses the latest stable version of Hugo.

Usage
===

Create a Heroku application using this buildpack:

```bash
$ heroku create --buildpack https://github.com/roperzh/heroku-buildpack-hugo.git
```

or configure your existent application:

```bash
$ heroku config:add BUILDPACK_URL="https://github.com/roperzh/heroku-buildpack-hugo.git"
```

Then simply git push to heroku and open your application!

```bash
$ git push heroku master
$ heroku open
```

Legacy Compatibility
===

For most pages this buildpack should work just fine. If, however, you're unable to deploy using this new version of the buildpack, you can get your app working again by locking it to the previous version:

```bash
heroku config:set BUILDPACK_URL=https://github.com/roperzh/heroku-buildpack-hugo#v0.12
git commit -am "Empty commit" --allow-empty
git push heroku master
```

Using themes
===

This buildpack provides a simple api to use custom themes, just add a `.hugotheme`
file in the root of your application with the url of your theme.

***Example***

To fetch the great [hyde](https://github.com/spf13/hyde.git) theme:

```
https://github.com/spf13/hyde.git
```

[Here](http://immense-hollows-6319.herokuapp.com/) is an example application,
and [here](https://github.com/roperzh/example-heroku-buildpack-hugo) is the code.

Alternative method
---

If you don't like the idea of a `.hugotheme` file, you can simply manage your
themes with [git submodules](http://git-scm.com/book/en/Git-Tools-Submodules).
Heroku will take care to fetch all the submodules in your project.

Important notes
===

Don't forget to configure your hugo `baseurl` with the url of your application.

Contributing
===

1- Fork it

2- Create your feature branch (git checkout -b my-new-feature)

3- Commit your changes (git commit -am 'Add some feature')

4- Push to the branch (git push origin my-new-feature)

5- Create new Pull Request
