Ledger Docker Image
===================

The unofficial docker image for the [ledger-cli][0] project.

[Docker Registry][1]

## Usage

Basic, but not very useful example:
```sh
docker run noazark/ledger --version
```

### Journal Data
The `.ledgerrc` file sets the `--file` flag to `-` which is stdin (I find this the most useful), so you can do this:
```sh
cat ./my-journal.dat | \
docker run -i noazark/ledger bal
```

### Volumes
If you'd rather use a volume, that's OK too:
```sh
docker run -i -v $PWD/data:/data noazark/ledger --file /data/my-journal.dat bal
```

### Using an Alias
If you're interested in using this to replace a local installation, consider making an alias:
```
# ~/.bashrc
alias ledger=docker run -i noazark/ledger
```


[0]: https://github.com/ledger/ledger
[1]: https://registry.hub.docker.com/u/noazark/ledger/
