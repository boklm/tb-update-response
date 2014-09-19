Tor Browser Update Responses script
===================================

This repository contains a script to generate responses for Tor Browser
updater.

See ticket [#12622](https://trac.torproject.org/projects/tor/ticket/12622)
for details.


Dependencies
------------

The following perl modules need to be installed to run the script:
  FindBin YAML File::Slurp Digest::SHA XML::Writer

On Debian / Ubuntu you can install them with:

```
  # apt-get install libfindbin-libs-perl libyaml-perl libfile-slurp-perl \
                    libdigest-sha-perl libxml-writer-perl
```

On Red Hat / Fedora you can install them with:

```
  # for module in FindBin YAML File::Slurp Digest::SHA XML::Writer
    do yum install "perl($module)"; done
```


URL Format
----------

The URL format is:
  https://something/$channel/$build_target/$os_version/$tb_version/$lang?force=1

'build_target' is the OS for which the browser was built. The correspo
ndance between the build target and the OS name that we use in archive
files is defined in the config.yml file.

'os_version' is the version of the OS we are running. This may be useful
later to tell people that their OS is no longer supported by Tor Browser.

'tb_version' is the Tor Browser version.

'lang' is the locale.

