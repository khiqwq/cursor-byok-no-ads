# Fork and modification notice

This repository is a modified distribution of [`leookun/cursor-byok`](https://github.com/leookun/cursor-byok).

## Changes in this fork

- Removed the runtime advertisement service and scheduled advertisement refresh loop.
- Removed the local advertisement asset cache and HTTP advertisement route.
- Removed advertisement UI entry points from the home screen.
- Removed upstream promotional/community links from the README and release notes.

## License and attribution

The upstream repository includes an MIT License. The original `LICENSE` file is retained unchanged. Copyright and license notices must remain with all redistributed copies and substantial portions of the source.

This fork is not affiliated with or endorsed by the upstream author, Cursor, or Anysphere. The `cursor-byok` name and any third-party trademarks remain subject to their respective owners.

## Verification status

- Frontend Vue template parsing: passed.
- Go formatting/static package checks: passed for packages that do not require generated protocol bindings.
- Full native build: not yet produced in this environment because the source archive does not include generated `cursor/gen/*` protocol bindings and the Wails binding generator/toolchain is not installed.
