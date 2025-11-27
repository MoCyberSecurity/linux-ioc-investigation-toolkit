Below are useful commands for verifying file integrity, comparing files, and generating bulk hashes during Linux-based IOC investigations.
# Linux IOC Investigation Toolkit: Hashing Quick Reference

This folder provides a practical command-line reference for **file hashing** on Linux. File hashing is essential for verifying file integrity, checking for malware or tampered files, sharing Indicators of Compromise (IOCs) with other analysts, and comparing suspicious files against known hashes.

## Common Hashing Commands

**SHA256 (256-bit):**
```bash
sha256sum <file>   # Generate SHA256 hash

## File Integrity & Hash Verification
---

### 1. Verify File Integrity

Compare the hash of a downloaded file with the official published hash:

```bash
sha256sum package.tar.gz

### 2. Compare Two Files

Check whether two files are identical by comparing their SHA256 hashes:

```bash
sha256sum file1.bin file2.bin

### 3. Bulk Hash Generation

Generate SHA256 hashes for **all files** in a directory and save them to `hashes.txt`:

```bash
find /path/to/files -type f -exec sha256sum {} \; > hashes.txt

This is useful for baseline creation, integrity checks, and detecting unexpected file changes.
