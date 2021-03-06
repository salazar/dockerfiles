## OpenResty Dockerfile

An Alpine-based OpenResty Dockerfile, including `luarocks` and using
LibreSSL.

## Usage

The application's home is configurable in the `docker-entrypoint`.sh
file; the default is `/app`.

Assuming the image built from this Dockerfile is tagged
`gmesalazar/openresty`, the command below will run a container exposing
port 8080 to the host and mapping our `app` dir to the container's
`/app`:

```
docker run -ti -p 8080:8080 -v $PWD/app:/app --user $UID:$GID gmesalazar/openresty
```

Flag `--user $UID:GID` makes sure any file created in the container
will have the same UID and GID as in the host.
