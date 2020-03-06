# Nightwatch

Nightwatch is a command line tool to easily handle events on file system modifications.

<img src="./nightwatch.jpg" width="300">

## Download

Download `nightwatch` from [releases](https://github.com/jakolehm/nightwatch/releases) page. Linux (amd64, arm64, armhf), MacOS and Windows are supported.


## Example Usage

Single file:
```bash 
$ find *.js | nightwatch node app.js
```

Watch everything in the current directory in a control loop:
```bash
COMMAND="bundle exec lolcat.rb"

while true; do
  if find . | nightwatch --debug --exit-on-change=255 --dir "${COMMAND}"; then
    break # command wants to terminate, exit code was success
  fi
  
  echo "Restart ${COMMAND}"
  sleep 1 
done
```

## Building From Source

```
$ make build
```
