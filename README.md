# Markdown Preview

A read-only Markdown preview rendered by Goldmark, registered as an Open With action. Use the floating preview icon to replace the editor, or the split button to show source and preview side by side. Native edits automatically update the preview.

Supports Markdown images, links (including automatic URL links), and GFM tables with column alignment. Images can use paths relative to the Markdown file within the workspace or HTTP(S) URLs. Links open workspace documents or the system browser. Image loading runs on a background worker and is cached for the preview session; unavailable images do not hide the document.

Uses the [Pencode](https://github.com/pencode-labs/pencode) peb v14 SDK. Requires Go 1.27.0 or newer.

## Build and install

```sh
git clone git@github.com:pencode-labs/markdown-preview.git
cd markdown-preview
go build -o bin/markdown-preview .
```

In Pencode's extension manager, choose **Install from local directory** and select this checkout. Extensions run on the workspace server, so build and install on that host for remote workspaces.

On Windows, build `bin/markdown-preview.exe` and set `entry` in `resources/extension.json` to `bin/markdown-preview.exe` before installing.

## Development

```sh
go test .
```

## License

MIT. See [LICENSE](LICENSE).

## Releases

Push a `v*` tag (for example, `v0.1.0`) to this repository, or publish a GitHub Release,
to test and build Linux, macOS and Windows packages for amd64 and arm64. The workflow
uploads ZIP archives and `SHA256SUMS` to the matching release, creating it if needed.
Prerelease tags such as `v0.1.0-rc.1` create prereleases.

Each ZIP contains `bin/`, `resources/`, the README and license. Its manifest uses the
tag version and the correct executable suffix for Windows. Download the package
for the workspace server's OS and architecture, extract it, then install the
extracted directory through Pencode's extension manager.
