# Important Notes About MongoDB



### GirdFS

The default maximum amount of size for BSON-documents is 16 MB. If we need to store document with a bigger size, we would use [GridFS ](https://docs.mongodb.com/manual/core/gridfs/) to do that.

This is a specification that divides the a file into parts, or chucks, and stores each chuck as a separate document. By default, GirdFS uses a chuck size of 255 kB; this is, GridFS divides a file into chucks of 255 kB  to store them.

