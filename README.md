# Traefik Buildpack

This is a [Heroku buildpack][0] for bundling a compatible [traefik][1]
binary with your environment.

## Versions

* Buildpack:   `0.3`
* traefik: `2.5.3` by default

## Usage

[Add this buildpack][2] to your Heroku application to install the `traefik` 
binary into the dynos:

```bash
$ heroku buildpacks:add https://github.com/banzera/heroku-buildpack-traefik.git
```

If you want to use a `traefik` version other than 2.5.3, set
`TRAEFIK_VERSION`:

```bash
heroku config:set TRAEFIK_VERSION="2.5.3"
```

### Clearing Repo Cache

Remember to clean your repository cache if you are updating the version of
buildpack. To do that, run:

```bash
$ heroku plugins:install https://github.com/heroku/heroku-repo.git
$ heroku repo:purge_cache -a appname
```

## Troubleshooting

If you run into issues when trying to deploy with this buildpack, make sure your
app is running on `cedar-14` or `heroku-16`. You can check this with:

```bash
$ heroku stack
```

[0]: http://devcenter.heroku.com/articles/buildpacks
[1]: https://traefik.io/
[2]: https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app
