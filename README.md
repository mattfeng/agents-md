# Create AGENTS.md

Generate or update `AGENTS.md` files from reusable templates.

## Usage

Run against the current directory:

```sh
uvx --from git+https://github.com/mattfeng/agents-md create-agents-md
```

Run with a specific target:

```sh
uvx --from git+https://github.com/mattfeng/agents-md create-agents-md --target /path/to/project
```

Pick templates explicitly:

```sh
uvx --from git+https://github.com/mattfeng/agents-md create-agents-md --template base --template python
```

Supplying `--template` skips the prompt. Repeat it for each template you want.

Available bundled templates:

- `base`
- `python`
- `sqlalchemy-alembic`
- `nextjs`
- `deep-learning`
- `jax-equinox`
- `pytorch`

List bundled templates:

```sh
uvx --from git+https://github.com/mattfeng/agents-md create-agents-md list
```

By default the command asks which templates to include. The base template is selected by default the first time; after that, rerunning against the same `AGENTS.md` uses the previous template choices as the prompt defaults. The user can still change any selection at the prompt.

Selected templates are rendered in an internal hierarchy regardless of prompt or `--template` order: general instructions first, then ecosystem templates, domain templates, and framework-specific templates. Templates that are not in the hierarchy are appended alphabetically.

Every run prints the resulting `AGENTS.md` content before saving it.

The generated section is wrapped in markers so rerunning the command updates only the managed block. Content outside those markers is preserved.

Templates are rendered with Jinja2. Bundled templates can use:

- `output_path`: target `AGENTS.md` path
- `project_dir`: target project directory
- `selected_templates`: list of selected template names
- `template_name`: the current template name
