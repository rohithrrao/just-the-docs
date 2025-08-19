<general_rules>
When working with SCSS styles, always use the two-file custom pattern: place variable definitions, functions, and mixins in `_sass/custom/setup.scss`, and place actual CSS styles in `_sass/custom/custom.scss`. The setup file is imported early in the cascade, while custom styles are imported last to allow overrides.

Before creating new SCSS components, search existing files in `_sass/` to see if similar functionality exists. Common SCSS files include `buttons.scss`, `navigation.scss`, `search.scss`, `typography.scss`, and `layout.scss`.

Always run `bundle exec rake search:init` before building the Jekyll site to generate the required search data JSON file. This is essential for the site's search functionality to work properly.

Use the provided npm scripts for code formatting and linting: run `npm run format` to format SCSS, JavaScript, and JSON files with Prettier, and `npm test` to lint SCSS files with Stylelint.

For local development, use the standard Jekyll workflow: run `bundle install` to install Ruby dependencies, then `bundle exec jekyll serve` to start the development server at `http://localhost:4000`.

When modifying Liquid templates, check both `_includes/` for reusable partials and `_layouts/` for page templates. The `_includes/components/` directory contains major UI components like navigation, header, footer, and search.

Docker development is supported via `docker-compose up` for containerized development environments.
</general_rules>

<repository_structure>
This is a Jekyll theme repository structured as a Ruby gem that provides documentation site functionality. The main theme files are distributed through the gem and include only `_layouts`, `_includes`, and `_sass` directories.

Key directories:
- `_sass/`: Contains all SCSS stylesheets organized by component (buttons, navigation, typography, etc.) with a `custom/` subdirectory for user customizations
- `_includes/`: Liquid template partials including a `components/` subdirectory for major UI elements and `css/` for SCSS liquid templates
- `_layouts/`: Page layout templates (default, minimal, page, post, etc.)
- `assets/`: Compiled CSS files and JavaScript, plus static images
- `docs/`: Documentation and examples for the theme itself
- `lib/tasks/`: Rake tasks, primarily for search functionality

The repository uses dual package management: Ruby gems managed via Bundler (Gemfile/gemspec) for Jekyll dependencies, and Node.js packages managed via npm (package.json) for development tools like Prettier and Stylelint.

Color schemes are defined in `_sass/color_schemes/` and can be extended by users. The `_sass/support/` directory contains variables, functions, and mixins used throughout the theme.
</repository_structure>

<dependencies_and_installation>
This repository uses dual package management requiring both Ruby and Node.js environments.

Ruby dependencies are managed via Bundler:
- Run `bundle install` to install Jekyll (>= 3.8.5), jekyll-seo-tag, rake, and other Ruby gems
- Dependencies are defined in `Gemfile` and `just-the-docs.gemspec`

Node.js dependencies are managed via npm:
- Run `npm install` to install development tools including Prettier, Stylelint, and SCSS configuration packages
- Dependencies are defined in `package.json` and used primarily for code formatting and linting

For containerized development, Docker and Docker Compose are supported with the provided `Dockerfile` and `docker-compose.yml` configuration.
</dependencies_and_installation>

<testing_instructions>
Testing in this repository focuses on SCSS linting and Jekyll build validation across multiple versions.

SCSS Testing:
- Run `npm test` to execute Stylelint on all SCSS files
- Stylelint configuration is defined in `.stylelintrc.json` with SCSS-specific rules and Prettier integration
- Files in `assets/css/just-the-docs-*.scss` and `_sass/vendor/` are excluded from linting

Jekyll Build Testing:
- CI automatically tests Jekyll builds across multiple Jekyll versions (3.9, 4.3) and Ruby versions (2.7, 3.1)
- Tests run on Ubuntu, macOS, and Windows environments
- Before any Jekyll build, `bundle exec rake search:init` must be run to generate search data
- Both gem-based builds and GitHub Pages builds are tested

The repository does not include traditional unit tests but relies on build validation and style checking to ensure code quality.
</testing_instructions>

<pull_request_formatting>
</pull_request_formatting>

