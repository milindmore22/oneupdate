## Important Files

- @docs/DEVELOPMENT.md: Detailed development guidelines, tools, directory tree map, and best practices.
- inc/: Contains the main plugin PHP code.
- assets/src/: Contains the source files for the plugin's assets (JavaScript, CSS).
- package.json: Contains our script commands.

## Important Notes

Use `wp-env` (v11 parallel environments setup) for local development and testing:

- `npm run wp-env start`: Start the governing site (port 8888).
- `npm run wp-env:child start`: Start the child/brand site (port 8890).
- `npm run wp-env:test start`: Start the test environment (port 8889).
- `npm run wp-env:cli -- composer install`: Install composer dependencies inside the CLI container.
- `npm run wp-env:child run cli -- --env-cwd=wp-content/plugins/oneupdate {command}`: Run WP-CLI commands in the child site container.
- `npm run test:php`: Run PHPUnit integration tests in the test environment.

Git Hooks:

- Pre-commit hook runs automatically using Lefthook. To manually check staged files:
  ```bash
  npx --no-install lint-staged
  ```
