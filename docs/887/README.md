# Cleanup Those Container Image Logs in Dockerfile

Here's something Billy added to my container Dockerfile image creator
thing to get rid of a bunch of the logs so people start out with
pristine ones that only represent what they have been doing:

```
... rm -rf /tmp/* /var/tmp/* /var/log/dmesg.* && \
     cat /dev/null > /var/log/dmesg && \
     cat /dev/null > /var/log/exim4/paniclog
```
