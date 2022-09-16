# Docker Playground

DOCKERFILE for constructing dev box without disrupt host machine for different situations. :)

## GUI application

For GUI application, prepare the `X Windows System` on the host machine, then add
`DISPLAY` to container environment like this:

```bash
expert DISPLAY=<your host machine IP address>
```
