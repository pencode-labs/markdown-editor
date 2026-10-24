# Markdown Editor

A Pencode editor extension with Markdown source editing and an HTML preview rendered by Goldmark.

Uses the [Pencode](https://github.com/pencode-labs/pencode) peb v6 SDK. Requires Go 1.27.0 or newer.

## Build and install

```sh
git clone https://github.com/pencode-labs/markdown-editor.git
cd markdown-editor
go build -o bin/markdown-editor .
```

In Pencode's extension manager, choose **Install from local directory** and select this checkout. Extensions run on the workspace server, so build and install on that host for remote workspaces.

On Windows, build `bin/markdown-editor.exe` and set `entry` in `resources/extension.json` to `bin/markdown-editor.exe` before installing.

## Development

```sh
go test ./...
```

## License

MIT. See [LICENSE](LICENSE).
