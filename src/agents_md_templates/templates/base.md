# Base instructions

## Planning
- Always prefer to construct general solutions that can be proven to work in all the expected cases, rather than implementing a series of "hacks" or special cases. Always be suspicious when something appears to require special cases.
- Address problems at the root cause, rather than patching over the symptoms.

## Files
- Before attempting to remove or modify a file/folder, check its file permissions. Furthermore, verify that its containing filesystem is writable: `target="$(readlink -f -- <path>)"; findmnt -no OPTIONS --target "$target"`. If the comma-separated mount options contain ro, treat the filesystem as read-only and do not attempt the edit. Report the limitation instead.
    - For a file that does not yet exist, run the check against its nearest existing parent directory.
- Do not try to remove or edit read-only files and folders.

## Networking
- For testing/exploration, access apps running on the host (e.g. Docker Compose) with `host.docker.internal` as the hostname.
- Actual applications in development, however, will be running on the host, and should access services via `localhost`.

## Verification
- Do not run applications, services, scripts, examples, demos, test suites, or other project code just to verify work unless the user explicitly asks.
- Static checks such as linting, formatting/style checks, and type checks are allowed.
