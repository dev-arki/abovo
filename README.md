# Abovo
Reproducible containerized development environment designed to provide deterministic tooling, eliminate host-machine dependency drift, and accelerate developer onboarding.

---
## 🚨 Why?
Modern development environments often suffer from:
* Inconsistent tool versions across machines.
* Time-consuming onboarding procedures.
* "Works on my machine" problems.
* Development workflows tightly coupled to host operating systems.

**Abovo** aims to solve these issues by defining the entire development environment as reproducible infrastructure.

---
## 🚀 Features
### 📌 Current
* Reproducible Dev Container configuration. ✅
* Pinned container base image. ✅
* Support for Visual Studio Code Dev Containers. ✅
* Arch Linux-based development environment. ✅
* Conditional build based in desired IDE. ✅
* Neovim support. ✅

### 🎯 Planned
* Neovim-first workflow support. 🔜
* User preference injection system. 🔜
* Automated host provisioning installer. 🔜

---
## 📋Requirements
* 📦 [Git](https://git-scm.com/)
* 🐋 [Docker](https://www.docker.com/)
* 🧩 [Visual Studio Code](https://code.visualstudio.com/) (*optional*)
* 🔌 [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) (*optional*)

---
## ⚡ Getting Started
### VS Code (Dev Containers Workflow)
The configuration targets the `vdev` multi-stage build, which initializes the core Arch Linux base image.
1. Clone the repository:
```bash
git clone https://github.com/dev-arki/abovo
cd abovo
```
2. Open the repository in Visual Studio Code and select:
```
Dev Containers: Reopen in Container
```
The development environment will be built automatically.

### Neovim (Docker CLI Workflow)
The standard Docker build pipeline targets the `ndev` stage by default, executing the package manager routines to provision Neovim on top of the base Arch Linux image.
1. Clone the repository:
```bash
git clone https://github.com/dev-arki/abovo
cd abovo
```
2. Build the development container image:
```bash
docker build -t abovo .
```
3. Instantiate and attach to the container interactively:
```bash
docker run -it --rm abovo bash
```

---
## 🧪 Project Status
**Current Phase:** Active (VsCode + Neovim Integration)

The core multi-stage containerization infrastructure (`vdev` and `ndev` environments) is operational. Development workflows for both Visual Studio Code and Neovim layers are structurally defined. Architecture and codebase integration are progressing actively; APIs and configuration layouts remain subject to modification prior to version stability.

---
## 📖 Documentation
Additional documentation is available in the [docs](docs/) directory.

---
## 🤝 Contributing
Contributions are welcome. By contributing to this project, you agree that your contributions will be licensed under the project's GNU GPLv3 License.

---
## License
Distributed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for more information.
