# wait until

script to retry a command until the return code is 0, print usage with `wait_until -h`

The parameter `--check` is only for structuring, the following commands are equivalent:

```bash
./wait_until -d 1 -r 3 -c 'grep text | wc -l | grep 1' -v 'cat wait_until'
```

```bash
./wait_until -d 1 -r 3 -v 'cat wait_until | grep text | wc -l | grep 1'
```
