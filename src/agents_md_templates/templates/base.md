# Base instructions

## Files
- Do not try to remove or edit read-only files and folders.

## Networking
- For testing/exploration, access apps running on the host (e.g. Docker Compose) with `host.docker.internal` as the hostname.
- Actual applications in development, however, will be running on the host, and should access services via `localhost`.

## Verification
- Do not run applications, services, scripts, examples, demos, test suites, or other project code just to verify work unless the user explicitly asks.
- Static checks such as linting, formatting/style checks, and type checks are allowed.
