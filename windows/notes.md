## Solution
`no_proxy="*" ansible -i ./hosts all -m win_ping`

## Refs
https://www.whatan00b.com/posts/debugging-a-segfault-from-ansible/
https://github.com/ansible/ansible/issues/32554

``` shell
rocket@MacBook-Air windows % ansible -i ./hosts all -m win_ping
objc[3884]: +[__NSCFConstantString initialize] may have been in progress in another thread when fork() was called.
objc[3884]: +[__NSCFConstantString initialize] may have been in progress in another thread when fork() was called. We cannot safely call it or ignore it in the fork() child process. Crashing instead. Set a breakpoint on objc_initializeAfterForkError to debug.
ERROR! A worker was found in a dead state
```
