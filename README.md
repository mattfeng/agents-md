# AGENTS.md templates

Generate or update `AGENTS.md` files from reusable templates.

## Usage

Run against the current directory:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md
```

Run with a specific target:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md --target /path/to/project
```

Pick templates explicitly:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md --template base --template python
```

Supplying `--template` skips the prompt. Repeat it for each template you want.

Available bundled templates:

- `base`
- `deep-learning`
- `jax-equinox`
- `nextjs`
- `python`
- `pytorch`

List bundled templates:

```sh
uvx --from git+https://github.com/mattfeng/agents-md agents-md list
```

By default the command asks which templates to include. The base template is selected by default in the prompt; project-specific templates are only included when the user chooses them.

Every run prints the resulting `AGENTS.md` content before saving it.

The generated section is wrapped in markers so rerunning the command updates only the managed block.

Templates are rendered with Jinja2. Bundled templates can use:

- `output_path`: target `AGENTS.md` path
- `project_dir`: target project directory
- `selected_templates`: list of selected template names
- `template_name`: the current template name
