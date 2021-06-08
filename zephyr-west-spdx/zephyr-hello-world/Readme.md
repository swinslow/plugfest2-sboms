Following build using instructions at https://github.com/swinslow/plugfest2-content/tree/main/zephyr-hello-world:

```
# for standard Zephyr west spdx output
> west spdx -d build -n https://swinslow.net/plugfest2-sboms/zephyr-hello-world/spdx

# for output with header includes
> west spdx -d build -n https://swinslow.net/plugfest2-sboms/zephyr-hello-world/spdx-with-headers \
>   -s build/spdx-with-headers \
>   --analyze-includes \
>   --include-sdk
```
