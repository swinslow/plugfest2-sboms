# Zephyr west spdx -- charge-controller-firmware

Build analysis SBOM, created using `west spdx` command built into Zephyr as of v2.6.0

See: https://docs.zephyrproject.org/latest/guides/west/zephyr-cmds.html#software-bill-of-materials-west-spdx

## Process

Following build using instructions at https://github.com/swinslow/plugfest2-content/tree/main/libre-solar-charge-controller-firmware/bin-rebuild:

```
# generate SPDX documents
> west spdx -d build -n https://swinslow.net/plugfest2-sboms/charge-controller-firmware/spdx

# generate more detailed SPDX documents, analyzing the header include files
> west spdx -d build -n https://swinslow.net/plugfest2-sboms/charge-controller-firmware/spdx-with-headers \
>   -s build/spdx-with-headers \
>   --analyze-includes \
>   --include-sdk
```

## Notes

See the Zephyr docs linked above for details about the multiple SPDX SBOMs that
are created as part of the above process.

The second version ("analyzing the header include files") also analyzes which C header
files are included during the build process. Some of these headers originate
from the [Zephyr SDK](https://github.com/zephyrproject-rtos/sdk-ng) and therefore
this one includes a fourth SBOM for those included files.
