Deploy:

```
$ deis create -a docs
$ deis config:set BUILDPACK_URL=https://github.com/heroku/heroku-buildpack-multi
$ deis healthchecks:set liveness httpGet 5000 --type web --initial-delay-timeout=5 --timeout-seconds=5
$ deis healthchecks:set readiness httpGet 5000 --type web --initial-delay-timeout=5 --timeout-seconds=5
$ git push deis master
```

