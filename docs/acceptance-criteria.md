# ACCPETANCE

## Phase 1 - Bootstrap
- Dev Container image builds and starts successfully. *succeed*
- VsCode detects the Dev container and attachs successfully. *succeed*
- Integrated terminal opens inside the container. *succeed*
- Arch linux is running inside the contianer. *succeed*
- Container rebuild succeeds. *succeed*

## Phase 2 - VsCode + Neovim Integration
- Dev Container image builds and starts successfully. *succeed*
- VsCode detects the Dev container and attachs successfully. *succeed*
- Neovim development environment can be built manually. *succeed*
- Container´s Neovim can be accessed cleanly. *succeed*
- Multi-stage build targets behave as designed. *succeed*

## Phase 3 - Non-root user setup *(current)*
- When accessing the container the `$ whoami` command returns a non-root username. *succeed*
- Dynamically conditional container build consistency. *succeed*
- VsCode & Neovim integration build and run as expected. *succeed*
