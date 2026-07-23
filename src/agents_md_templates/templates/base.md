# Base instructions

## Planning
- Always prefer to construct general solutions that can be proven to work in all the expected cases, rather than implementing a series of "hacks" or special cases. Always be suspicious when something appears to require special cases.
- Address problems at the root cause, rather than patching over the symptoms.

## Files
- Before attempting to remove or modify a file/folder, check for read-only status (e.g. permissions and read-only file systems).
- Do not try to remove or edit read-only files and folders.

## Networking
- For testing/exploration, access apps running on the host (e.g. Docker Compose) with `host.docker.internal` as the hostname.
- Actual applications in development, however, will be running on the host, and should access services via `localhost`.

## Verification
- Do not run applications, services, scripts, examples, demos, test suites, or other project code just to verify work unless the user explicitly asks.
- Static checks such as linting, formatting/style checks, and type checks are allowed.
