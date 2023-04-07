# wait until

script to retry a command until the return code is 0, print usage with `wait_until -h`

The parameter `--check` is only for structuring, the following commands are equivalent:

```bash
wait_until --delay 1 --retries 3 -c 'grep text | wc -l | grep 1' --verbose 'cat wait_until'
```

```bash
wait_until --delay 1 --retries 3 --verbose 'cat wait_until | grep text | wc -l | grep 1'
```

## wait until with curl

```bash
wait_until -delay 10 -retries 42 --check 'grep 402' 'curl --no-progress-meter --connect-timeout 10 --retry 42 --retry-delay 10 --output /dev/null/ --write-out "%{http_code}" http://example.com/api/endpoint'

wait_until -v -d 1 -r 5 -c 'grep -e 100 -e 404' 'curl --silent --no-progress-meter --connect-timeout 5 --retry 5 --retry-delay 1 --write-out "%{http_code}" http://example.com/api/endpoint'
```
