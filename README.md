# MetaHash
Metahash (Hashed FileVersionInfo)

The Metahash is a product of concatenating the following FileVersionInfo strings (as is, no separators):
- CompanyName
- FileDescription
- InternalName
- LegalCopyright
- LegalTrademarks
- OriginalFilename
- ProductName

Metahashes have a bit less entropy and they can match more malware, but are also prone for false positives. Not that no version numbers (which changes freqnently) are included in the hashing process.

![Test Image ](Corellation.png)

*Images showing Metahash (left), Richhash (middle) and conventional file hashes (right), showing relationships over other hashes.
Please not that not all files have Richheaders or Filversioninfo though.*

Result is shown as:
- mh: MD5_HASH = File contains FileVersionInfo (at least one string)
- \- = Contains absolutely no FileVersionInfo strings.

Example CSV file (**mh_rh_md5_sha1_sha256.csv**) included in this folder.
Fields in CSV file:
- Metahash ("mh:")
- Richhash ("rh:", "nh:")
- MD5
- SHA1
- SHA256

**Tool:** Metahash.zip

Usage: Metahash.exe FILENAME
Produces a hash of Filversion info strikgs, i.e.:

c:\> metahash Metahash.exe 
mh:636a13ef8c5eea079d5a264dab77684a
