# Deploy PID Cloud

This bundle contains one static app that can be published to GitHub Pages or Azure Static Web Apps. Keep the files together in the repository root so `index.html`, the campus artwork, and the platform config stay side by side.

## GitHub Pages

1. Create a GitHub repository and upload the files at the ZIP root.
2. Open **Settings → Pages**.
3. Set **Build and deployment** to **Deploy from a branch**, choose `main` and `/(root)`, then save.
4. GitHub will show the published site URL on the Pages settings screen.

## Azure Static Web Apps

1. Create an Azure Static Web App and connect it to this GitHub repository, using branch `main` and app location `/` (no API or build output folder).
2. In the repository's **Settings → Secrets and variables → Actions**, add `AZURE_STATIC_WEB_APPS_API_TOKEN` with the deployment token from the Azure Static Web App.
3. Push to `main`. The included GitHub Actions workflow publishes the root static files to Azure.

The workflow assumes the repository is named or connected in Azure; Azure supplies its deployment token. The HTML preview for DOCX and Excel loads libraries from public CDNs, so those previews need internet access.

## Storage note

Uploads use local IndexedDB and byte-exact 300 KiB parts, so download reassembles the original. This is chunking, not guaranteed lossless compression to 350 KB total. The browser's local quota limits total storage; the 2 TB label is a capacity target, not real cloud storage. Hosting this page on GitHub or Azure does not make uploaded files shared or cloud-stored. That needs a separate backend and authentication.
