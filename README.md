NNG Meson Patch

clone to same dir name as nng:

```
git clone https://github.com/argylelabcoat/nng-meson-patch nng-1.1.1
```

build release zip:

```
cd ..
zip -r9 nng-patch-v1.1.1.zip ./nng-1.1.1 -x *.git* build/\* README.md nng.wrap
sha256sum nng-patch-v1.1.1.zip
```
