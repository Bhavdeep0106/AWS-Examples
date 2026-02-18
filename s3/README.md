# S3 – Fast Revision Notes

---

# 1. Bucket Naming Rules

- 3 to 63 characters
- Lowercase letters, numbers, . and - only
- Must start and end with letter or number
- No double dots
- Cannot look like an IP address
- No reserved prefixes: xn--, sthree-, sthree-configuration-
- No reserved suffixes: -s3alias, --ol-s3
- Must be globally unique
- No dots if using Transfer Acceleration

---

# 2. Bucket Restrictions and Limits

- 100 buckets default
- Up to 1000 with request
- Must empty bucket before deleting
- No max bucket size
- No limit on number of objects
- Object size: 0 bytes to 5 TB
- Over 100 MB use Multipart Upload
- Outposts has limits
- GET, PUT, LIST, DELETE are highly available
- Create, Delete, Config changes should be done less often

---

# 3. Bucket Types

Amazon S3 has 2 types of buckets:

## General Purpose Buckets

- Flat hierarchy
- Original type
- Recommended for most use cases
- Works with all storage classes except S3 Express One Zone
- No prefix limits
- Default limit: 100 per account

## Directory Buckets

- Folder hierarchy
- Only with S3 Express One Zone
- Single digit millisecond PUT and GET
- No prefix limits
- Directories scale horizontally
- Default limit: 10 per account

---

# 4. S3 Folders

- Not real folders
- Just objects with prefix

When created:
- Zero byte object
- Ends with `/`
- Example: `myfolder/`

Key points:
- No separate metadata or permissions
- Cannot be full or empty
- Moving folder = renaming objects with same prefix

---

# 5. S3 Object Overview

- Objects represent data, not infrastructure

Key features:
- ETag: detects content change
- Checksums: integrity validation
- Prefixes: simulate folders
- Metadata: descriptive info
- Tags: object level tagging
- Object Lock: immutability
- Versioning: multiple versions

---

# 6. S3 Objects – ETags

## What is an ETag

- HTTP response header
- Detects content change without download
- Usually a hash like MD5 or SHA-1
- Used for cache validation

## In S3

- Every object has an ETag
- Based on object content only
- Changes when content changes, not metadata
- May not be MD5 if encrypted or multipart
- Identifies a specific object version

Use case:
- Detect object content changes programmatically

---

# 7. S3 Objects – Checksums

## What is a Checksum

- Used to verify data integrity
- Detects corruption during upload or download
- Ensures file was not altered in transit

## In S3

- S3 verifies integrity on upload and download
- You can choose checksum algorithm during upload

## Supported Algorithms

- CRC32
- CRC32C
- SHA1
- SHA256

Memory:
Checksum = integrity check  
ETag = change detection
