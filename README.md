# Vue Issues Forms

Playground for a https://new-issue.vuejs.org equivalent using issues forms

  - There aren't conditional fields. A project could create one .yml issue form for each language and issue type and let them users choose (in the same way they choose if something is a Bug Report or a Feature Request)

  - Instead of the version combo box, following how [Vite bug reports](https://github.com/vitejs/vite/issues/new?assignees=&labels=pending+triage&template=bug_report.yml) works we are asking this info directly with the system info asking users to run `envinfo` in their projects
    ```
    npx envinfo --system --npmPackages vite,@vitejs/plugin-vue --binaries --browsers
    ```
    Note: A version combo box could be done by each repo editing the yml to add the tag during release in each project.

  - Issues Forms doesn't work on mobile (this could count as a feature, uses shouldn't use mobile to report an issue

  - In [Vite issues](https://github.com/vitejs/vite/issues/new?assignees=&labels=pending+triage&template=bug_report.yml) we include a series of required checkboxes that users need to tick before being able to submit. For Vitepress for example they look like
    ```yml
    - type: checkboxes
      id: checkboxes
      attributes:
        label: Validations
        description: Before submitting the issue, please make sure you do the following
        options:
          - label: Follow our [Code of Conduct](https://vuejs.org/coc)
            required: true
          - label: Read the [docs](https://vitepress.vuejs.org/).
            required: true
          - label: Check that there isn't already an issue that reports the same bug to avoid creating a duplicate.
            required: true
    ```
    This is good to reinforce some checks that were described in the form description. The problem with these required checkboxes is that there isn't a way to avoid showing them in the final issue so the final issue is a bit more cluttered.