# AGENTS.md templates

Generate or update `AGENTS.md` files from reusable templates.

## Usage

Run from GitHub:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md write --target /path/to/project
```

Run against the current directory:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md write
```

Preview without writing:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md write --dry-run
```

Pick templates explicitly:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md write --template base --template python
```

Supplying `--template` skips the prompt. Repeat it for each template you want.

List bundled templates:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md list
```

By default the command asks which templates to include. The base template is selected by default in the prompt; project-specific templates are only included when the user chooses them.

The generated section is wrapped in markers so rerunning the command updates only the managed block.
