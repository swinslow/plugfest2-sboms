# Zephyr west spdx -- hello-world

Build analysis SBOM, created using `west spdx` command built into Zephyr as of v2.6.0

See: https://docs.zephyrproject.org/latest/guides/west/zephyr-cmds.html#software-bill-of-materials-west-spdx

## Process

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

## Notes

See the Zephyr docs linked above for details about the multiple SPDX SBOMs that
are created as part of the above process.

The second version ("output with header includes") also analyzes which C header
files are included during the build process. Some of these headers originate
from the [Zephyr SDK](https://github.com/zephyrproject-rtos/sdk-ng) and therefore
this one includes a fourth SBOM for those included files.
