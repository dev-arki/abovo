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

### 🎯 Planned
* Neovim-first workflow support. 🔜
* User preference injection system. 🔜
* Automated host provisioning installer. 🔜

---
## 📋Requirements
* 📦 [Git](https://git-scm.com/)
* 🐋 [Docker](https://www.docker.com/)
* 🧩 [Visual Studio Code](https://code.visualstudio.com/)
* 🔌 [Dev Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

---
## ⚡ Getting Started
```bash
git clone https://github.com/dev-arki/abovo
cd abovo
```
Open the repository in Visual Studio Code and select:
```
Dev Containers: Reopen in Container
```
The development environment will be built automatically.

---
## 🧪 Project Status
**Current phase:** Bootstrap.
The project is under active development and should be considered experimental. Interfaces, configuration formats, and implementation details may change without notice until a stable release is published.

---
## 📖 Documentation
Additional documentation is available in the [docs](docs/) directory.

---
## 🤝 Contributing
Contributions are welcome. By contributing to this project, you agree that your contributions will be licensed under the project's GNU GPLv3 License.

---
## License
Distributed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for more information.
