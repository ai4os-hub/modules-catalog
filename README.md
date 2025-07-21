<div align="center">
  <img src="https://ai4eosc.eu/wp-content/uploads/sites/10/2022/09/horizontal-transparent.png" alt="logo" width="500"/>
</div>

# AI4OS Modules catalog

[![Conventional Commits](https://img.shields.io/badge/Conventional%20Commits-1.0.0-%23FE5196?logo=conventionalcommits&logoColor=white)](https://conventionalcommits.org)

This catalog gathers all the AI modules integrated in the AI4OS Marketplace.
AI modules are listed as git submodules.


### Adding a module to the catalog

To add a module to the catalog:
```bash
git submodule add https://github.com/ai4os-hub/<module_name>
```

If the user has a default branch different from `master` (eg. `main`),
you should add this parameter in the submodule command:

```bash
git submodule add -b main https://github.com/ai4os-hub/<module_name>
```

Remember that for a new module to appear in the Dashboard, you need to **trigger the Jenkins pipeline** of that module after _pushing_ the catalog index update, so that PAPI is notified that it has to refresh the catalog.
Otherwise your module will end up appearing nonetheless after a period of 7 days.


### Removing a module from the catalog

To remove a module from the catalog:
```bash
bash utils/remove-submodule.sh <module_name>
```

### Updating the existing modules

To update the existing modules:
```bash
git pull --recurse-submodules
git submodule update --remote --recursive
```
