logstash-fixed
==============

An updated logstash compatible with filebeat

Description
-----------

The official dockerized logstash repository had old plugin versions which are not working with the latest filebeat (or any other datashippers anyway).
This version is just the same with an updated version of logstash-input-beats

See [This issue on filebeat github](https://github.com/elastic/filebeat/issues/229) for more informations

Usage
-----

With this sample configuration file (test.json) in the current directory :
```
  input{
    beats{
      port=>5044
    }
  }
  output{
    stdout{}
  }
```

Launch logstash (interactive) with :
```sh
    docker run -it -p 5044:5044 -v "$PWD":/config-dir logstash-fix -f /config-dir/test.json
```

Version
-------

This repository is based on logstash:2.0.0-1 version

logstash-input-beats if upgraded from version 0.9.2 to 0.9.6

