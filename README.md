### usage

```
cd <distro>
cp ~/scylla/build/release/dist/tar/scylla-unified-package-x.y.z.tar.gz scylla-unified-package.tar.gz
docker image build -t scylla-supervisor-test:1 .
docker container run scylla-supervisor-test:1
```
