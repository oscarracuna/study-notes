
We can also find information about the installed plugins by reviewing the source code manually by inspecting the page source or filtering for the information using [[curl]] and other command-line utils.

## Plugins
```
curl -s -X GET http://[url] | sed 's/href=/\n/g' | sed 's/src=/\n/' | grep 'wp-content/plugins/*' | cut -d "'" -f2
```

## Themes
```shell
curl -s -X GET http://[url] | sed 's/href=/\n/g' | sed 's/src=/\n/g' | grep 'themes' | cut -d"'" -f2
```

## Plugin Active Enumeration
```shell
curl -I -X GET http://[url]/wp-content/plugins/mail-masta
```
Of course, if the file does not exist, we will receive a 404 not found.
Of course, you can use [[wfuzz]], [[WPscan]], or any dir searcher.