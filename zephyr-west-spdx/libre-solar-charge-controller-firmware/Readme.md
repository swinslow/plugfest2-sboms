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
