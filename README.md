# docker-chm-generator

This is a docker container that will generate a `chm` file from an `asciidoc`
(not `asciidoctor`) document.

## Usage

The container expects a mount for the `/src` folder that contains the
`index.adoc` that will be compiled, and another mount on `/out` where the
`index.chm` will be written.

Assuming in the current folder there is an `index.adoc` file:

```sh
docker run -it \
           --rm \
            -v `pwd`/src \
            -v `pwd`:/out \
            bmst/chm-generator
```

This will generate a file named `index.chm` into the current folder.

