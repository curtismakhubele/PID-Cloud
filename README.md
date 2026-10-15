# PID Cloud Drive

A single-page document workspace with the supplied PID Cloud over UNISA campus artwork. It supports document upload, search, previews, notes, and download.

For hosting instructions, see [DEPLOY.md](DEPLOY.md). Uploads are stored in the current browser's IndexedDB as byte-exact 300 KiB parts and reconstructed on download. Parts are under 350 KB; total document size is not. Lossless compression cannot guarantee every arbitrary file fits below 350 KB. Browser quota varies, and this is local browser storage rather than shared cloud storage. The 2 TB display is a capacity target only.
