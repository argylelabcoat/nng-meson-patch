NNG Meson Patch

clone to same dir name as nng:

```
git clone https://github.com/argylelabcoat/nng-meson-patch nng-1.1.1
```

build release zip:

```
zip -r9 ../nng-patch-v1.1.1.zip ./ -x *.git* build/\*
sha256sum ../nng-patch-v1.1.1.zip
```
