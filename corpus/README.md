# README

This subdirectory stores the IDLs for `github.com/go-nlp/corpus`.

Instructions to compile the IDLs follow:

## Flatbuffers

```
cd /PATH/TO/THIS/SUBDIRECTORY
flatc -g --go-namespace "fb" -o /PATH/TO/corpus/internal/serialization *.fbs
```

This will generate files in `"github.com/go-nlp/corpus/internal/serialization/fb"`, which is also the package name that will be used.

## Protobuf

```
cd /PATH/TO/THIS/SUBDIRECTORY
protoc -I=. --go_out=$OUT_DIR corpus.proto
```

About `$OUT_DIR` - let's say the `github.com/go-nlp/corpus` repository is sitting in `/home/me/code/github.com/go-nlp/corpus`, then `$OUT_DIR` should be `/home/me/code`. This is because `protoc` will automatically create all the relevant directories.

This will generate files in `"github.com/go-nlp/corpus/internal/serialization/pb"`, which is also the package name that will be used.
