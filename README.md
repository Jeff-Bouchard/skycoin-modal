# skycoin-modal

WIP skycoin payment modal web application for integration with snipcart.com as a custom payment gateway

Hugo is used to generate the html templates and page resources

**The escaped functions (which need to appear in the final template files generated by hugo) are defined in [config.toml](/config.toml)**

Tested on Archlinux

## Prerequisite

```
yay -S go hugo skycoin-explorer skycoin-bin
```
Note: the skycoin explorer will be added to the [.deb package repo](https://the-sycoin-project.github.io) soon.

Additionally, to live reload the application you will need:
```
go get github.com/pilu/fresh
sudo ln -s ~/go/bin/fresh /usr/bin/fresh
```

(Alternatively, you can add GOBIN to your PATH)

## Sync Dependencies

Sync the needed golang dependencies
```
go mod init
go mod vendor -v
```

## Build the Frontend with Hugo

Build the front end
```
hugo -D
```

Live-editing the hugo templates is also possible, this is done independent of the golang web application.

```
hugo server -D
```

## Build the statik/statik.go file (not yet implemented)
(requires the statik binary)
```
go generate
```

the contents of the `public` folder which was created by hugo in the previous step can now be compiled into the binary.


## Run the application
```
make fresh
```

starts on :
[http://127.0.0.1:8041](http://127.0.0.1:8041)
