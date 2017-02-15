# EnvSubst

When a program does not know about environment variables, you can still use them. You just have to create a template that specifies where the env vars go, then use `envsubst` to populate the values and save to a stamped file. E.g.:
```sh
envsubst < /etc/nginx/conf.d/mysite.template > /etc/nginx/conf.d/default.conf
```
since nginx doesn't interpret env vars in most parts of config files. [Docs](https://www.gnu.org/software/gettext/manual/html_node/envsubst-Invocation.html).
