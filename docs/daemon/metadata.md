# Metadata processing

The indexer isn't interested in the actual contents of large files,
altough it might be interested in parts of smaller files.

The relevant meta-data mostly consists of things like mime-types,
the size of a picture, when it was created, etc.
Query terms of most relevance are names rather than for example the genre of a song.

One of the most important and basic roles of the project is as an application launcher,
which is based on mime-types almost entierly.

Regarding mime-types, there are some rust libraries:
+ https://bitbucket.org/joshmorin/mimty
+ https://github.com/hyperium/mime.rs
+ https://github.com/conduit-rust/mime-types

Regarding [EXIF](https://en.wikipedia.org/wiki/Exchangeable_image_file_format) and other metadata formats:
+ https://github.com/netvl/immeta (pure rust implementation)
+ https://github.com/felixc/rexiv2 (depends on gexiv2)
