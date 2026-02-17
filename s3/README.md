# S3 Bucket Naming Rules – Simple Version

## 1. Length
- Must be **3 to 63 characters**

Memory: Minimum 3, Maximum 63

---

## 2. Allowed Characters
- Lowercase letters only  
- Numbers  
- Dots `.`  
- Hyphens `-`

Memory: small letters, numbers, dot, dash

---

## 3. Start and End Rule
- Must **start with a letter or number**
- Must **end with a letter or number**

Memory: No dot or dash at the edges

---

## 4. No Double Dots
- Cannot contain `..`

Example:  
- ❌ my..bucket  
- ✅ my.bucket  

---

## 5. Cannot Look Like an IP Address
- Cannot be formatted like: `192.168.1.1`

Memory: No IP-style names

---

## 6. Restricted Prefixes
Cannot start with:
- `xn--`
- `sthree-`
- `sthree-configuration-`

Memory: Some AWS system prefixes are reserved

---

## 7. Restricted Suffixes
Cannot end with:
- `-s3alias`
- `--ol-s3`

Memory: Reserved for AWS

---

## 8. Must Be Globally Unique
- Bucket name must be unique across all AWS accounts worldwide

Memory: One name globally

---

## 9. Transfer Acceleration Rule
- If using S3 Transfer Acceleration
- Bucket name cannot contain dots

Memory: Acceleration = no dots

---

# 30-Second Recall Version

3–63 characters  
Lowercase only  
Start and end clean  
No double dots  
Not an IP  
No reserved prefix or suffix  
Globally unique  
No dots with acceleration
