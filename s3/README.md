# S3 – Fast Revision Notes

---

# 1. Bucket Naming Rules

- 3 to 63 characters  
- Lowercase letters, numbers, . and - only  
- Start and end with letter or number  
- No double dots  
- Cannot look like an IP address  
- No reserved prefixes: xn--, sthree-, sthree-configuration-  
- No reserved suffixes: -s3alias, --ol-s3  
- Must be globally unique  
- No dots with Transfer Acceleration  

---

# 2. Bucket Restrictions and Limits

- 100 buckets default  
- Up to 1000 with request  
- Empty bucket before deleting  
- No max bucket size  
- No limit on objects  
- Object size: 0 bytes to 5 TB  
- Over 100 MB use Multipart Upload  
- Outposts has limits  
- GET, PUT, LIST, DELETE are highly available  
- Create and config changes less frequent  

---

# 3. Bucket Types

## General Purpose Buckets
- Flat structure  
- Default S3 type  
- Used for most cases  
- Works with all storage classes except S3 Express One Zone  
- No prefix limits  
- 100 per account default  

## Directory Buckets
- Folder structure  
- Only with S3 Express One Zone  
- Very low latency PUT and GET  
- No prefix limits  
- Directories scale horizontally  
- 10 per account default  

---

# 4. S3 Folders

- Not real folders  
- Just objects with prefix  
- Creating folder = zero byte object  
- Name ends with /  
- No separate metadata  
- Cannot be full or empty  
- Moving folder = rename objects with same prefix  

---

# 5. S3 Object Overview

- Objects represent data  
- Not infrastructure  

Key features:
- ETag = content change detection  
- Checksum = integrity validation  
- Prefix = grouping method  
- Metadata = object description  
- Tags = object level tagging  
- Object Lock = immutability  
- Versioning = multiple versions  

---

# 6. ETags

- HTTP response header  
- Detects content change  
- Based on object data only  
- Does not change for metadata updates  
- May not be MD5 if encrypted or multipart  
- Represents specific object version  

Use: Detect content changes programmatically  

---

# 7. Checksums

- Verifies data integrity  
- Detects corruption in transit  
- Used during upload and download  
- Algorithm chosen during upload  

Supported:
- CRC32  
- CRC32C  
- SHA1  
- SHA256  

Checksum = integrity  
ETag = change detection  

---

# 8. Object Prefixes

- Prefix = string before filename  
- Part of object key  

Example:  
`/assets/images/andrew.png`  
Prefix = `/assets/images/`  
Filename = `andrew.png`  

- S3 uses flat structure  
- Prefix helps organize and filter  
- Uses `/` as delimiter  
- Not real folders  
- No limit on number of prefixes  
- Object key max size = 1024 bytes  

Memory:
Prefix = grouping tool in flat storage
