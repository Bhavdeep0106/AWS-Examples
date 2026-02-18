## Create a new s3 bucket

```md
aws s3 mb s3://checksums-example-bd-2345
```

## Create a file that will we do a checksum on
```md
md5sum myfile.txt
# 6f5902ac237024bdd0c176cb93063dc4  myfile.txt
```
## Upload our file and look at its etag

```
aws s3 cp myfile.txt s3://checksums-example-bd-2345
aws s3api head-object --bucket checksums-example-bd-2345 --key myfile.txt
```

## upload a file with a diff checksum

--