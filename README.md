# splunkify
This tiny script decorates any executable output with minimal info in oderd to be easily collected by [Splunk](www.splunk.com) agent.

## Usage examples

Invoke it before your plain command/executable (ex. ls ...)
```shell
$ ./splunkify ls -sh /tmp

2021-09-27 09:37:19.959 INFO total 3.5M
2021-09-27 09:37:20.020 INFO 1.0K file1
2021-09-27 09:37:20.080 INFO 1.0K file2
2021-09-27 09:37:20.260 INFO 1.3M file3
2021-09-27 09:37:20.323 INFO 2.2M file4
```

It converts stderr output into error logs also:

```
$ ./splunkify cat nofile.txt

2021-09-27 09:30:45.113 ERROR cat: nofile.txt: No such file or directory
```

