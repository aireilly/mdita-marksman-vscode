# MDITA Marksman VSCode

> [!NOTE]
> This project is a fork of [marksman-vscode](https://github.com/artempyanykh/marksman-vscode) by Artem Pyanykh, extended with support for [Lightweight DITA (LwDITA)][lwdita] MDITA authoring. 
> The upstream extension provides Markdown language-server features via [Marksman][upstream]; this fork replaces the server with [MDITA Marksman][mn], which adds MDITA-specific capabilities such as `.mditamap` support and DITA front-matter handling.

Integrates the [MDITA Marksman][mn] language server into VSCode for Markdown and
MDITA authoring.

## Features

- **Cross-references**: navigate and manage references between documents.
- **Completion**: context-aware suggestions for wiki links, reference links, and headings.
- **Diagnostics**: real-time warnings for broken links and other issues.
- **Hover preview**: inline preview of linked content.
- **Find references**: locate all references to a symbol across your workspace.
- **Follow links**: navigate through document links.
- **MDITA Map support**: dedicated language support for `.mditamap` files.

## Installation

1. Install the extension from the VSCode Marketplace or from a `.vsix` package:
   ```
   code --install-extension mdita-marksman-0.0.1.vsix
   ```
2. Add a `.mdita-marksman.toml` file to your workspace root folder. The
   extension activates only when this file is present to avoid running on
   unrelated Markdown files.
3. The extension automatically downloads the compatible `mdita-marksman` language
   server binary from [GitHub releases][mn-releases]. Supported platforms:
   - Windows x64
   - macOS x64 and ARM64
   - Linux x64 and ARM64

   Alternatively, you can place the `mdita-marksman` binary somewhere on your
   `PATH`, or build it from [source][mn].

## Commands

- **MDITA Marksman: Restart Server** - restart the language server.
- **MDITA Marksman: Show Output** - display the server output log.

## Extension Settings

- **Custom Command** (`mdita-marksman.customCommand`): specify a custom command
  to start the language server.
- **Custom Command Dir** (`mdita-marksman.customCommandDir`): set the working
  directory for the custom command.
- **Trace: Server** (`mdita-marksman.trace.server`): set the verbosity level for
  server communication (`off`, `messages`, or `verbose`).

## Development

- Run `npm install` to install dependencies.
- Run `npm run webpack-dev` or press F5 to start development/debugging.
- Run `npm run lint` to lint the source.

### Packaging

1. Install vsce: `npm install -g @vscode/vsce`
2. Package: `vsce package`
3. Publish: `vsce publish`

## License

[MIT](LICENSE)

[mn]: https://github.com/aireilly/mdita-marksman
[mn-releases]: https://github.com/aireilly/mdita-marksman/releases
[upstream]: https://github.com/artempyanykh/marksman
[lwdita]: https://docs.oasis-open.org/dita/LwDITA/v1.0/LwDITA-v1.0.html
