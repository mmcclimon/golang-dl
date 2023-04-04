# golang.org/dl

This repository holds the Go wrapper programs that run specific versions of Go, such
as `go install golang.org/dl/go1.10.3@latest` and `go install golang.org/dl/gotip@latest`.

## Report Issues / Send Patches

This repository uses Gerrit for code changes. To learn how to submit
changes to this repository, see https://golang.org/doc/contribute.html.
The main issue tracker for the net repository is located at
https://github.com/golang/go/issues. Prefix your issue with "dl:" in the
subject line, so it is easy to find.

## michael tweaks + how to

- the patch is a tiny one, to download to $GOPATH/sdk instead of $HOME/sdk,
  because _honestly_
- to install go1.19 (for example): `go install ./go1.19`
- probably, you want to set GOBIN so things install to the version-correct bin
  dir: `go1.19 env -w GOBIN=$(go1.19 env GOROOT)/bin`
- then, in your .envrc file for whatever:

```
export GOROOT="$(go1.19 env GOROOT)"
PATH_add "$(go1.19 env GOROOT)/bin"
```
