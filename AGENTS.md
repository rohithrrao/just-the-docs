<general_rules>
- Always check existing SCSS files in `_sass/` before creating new styles - the theme has organized stylesheets by component (base.scss, buttons.scss, code.scss, navigation.scss, etc.) with subdirectories for utilities, color schemes, and vendor files
- When modifying search functionality, run `bundle exec rake search:init` to regenerate the search data file (`assets/js/zzzz-search-data.json`) after making changes
- Use `npm test` to run CSS/JS linting with Stylelint before committing changes - this ensures code quality and consistency
- Use `npm run format` to format code with Prettier according to the project's style guidelines (2-space tabs, no semicolons, double quotes, LF line endings)
- Follow Jekyll gem conventions - only files in `_layouts`, `_includes`, and `_sass` are included in the gem distribution
- For local development, use `bundle exec jekyll serve` to start the development server
- The theme follows these design principles: minimal dependencies, no build script needed, mobile-first design, content-focused approach
</general_rules>

<repository_structure>
This is a Jekyll theme distributed as a Ruby gem with the following key directories:

- `_sass/` - SCSS stylesheets organized by component with subdirectories:
  - `color_schemes/` - Light and dark theme definitions
  - `custom/` - Custom styling setup and overrides
  - `support/` - Variables, functions, and mixins
  - `utilities/` - Utility classes for colors, layout, spacing, typography
  - `vendor/` - Third-party stylesheets
- `_includes/` - HTML partials and components:
  - `components/` - Reusable UI components (navigation, header, footer, search)
  - `icons/` - SVG icon definitions
  - `css/` - Liquid-processed SCSS files
  - `js/` - JavaScript includes
  - `lunr/` - Search functionality components
- `_layouts/` - Page templates (default.html, minimal.html, page.html, post.html, etc.)
- `docs/` - Theme documentation and examples:
  - `ui-components/` - Documentation for buttons, callouts, code blocks, etc.
  - `utilities/` - Documentation for utility classes
- `lib/tasks/` - Rake tasks, primarily `search.rake` for search functionality setup
- `bin/` - Executable scripts including `just-the-docs` for running rake tasks
- `assets/` - Static assets including CSS entry points and JavaScript files
</repository_structure>

<dependencies_and_installation>
This repository uses two package managers:

**Ruby/Jekyll Dependencies:**
- Run `bundle install` to install Jekyll and theme dependencies
- Runtime dependencies include Jekyll (>=3.8.5), jekyll-seo-tag (>=2.0), and rake (>=12.3.1)
- Uses Bundler for dependency management as defined in the gemspec file

**Node.js Development Tools:**
- Run `npm install` to install development tooling for code quality
- Includes Prettier for code formatting and Stylelint for SCSS linting
- Development dependencies are used for maintaining code quality but not required for theme usage
</dependencies_and_installation>

<testing_instructions>
The repository uses GitHub Actions CI with multiple test jobs:

**Jekyll Build Testing:**
- Tests Jekyll builds across multiple Ruby versions (2.7, 3.1) and Jekyll versions (3.9, 4.3) on Ubuntu, macOS, and Windows
- Also tests GitHub Pages compatibility using `fixtures/Gemfile-github-pages`
- Run `bundle exec jekyll build` locally to test builds

**CSS/JS Quality Testing:**
- Run `npm test` to execute Stylelint on all SCSS files
- The linting configuration uses stylelint-config-standard-scss and stylelint-config-prettier-scss
- Ignores vendor files and generated CSS files as defined in `.stylelintrc.json`
</testing_instructions>

<pull_request_formatting>
</pull_request_formatting>

