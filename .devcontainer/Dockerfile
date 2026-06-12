# *[=============== SET & PIN ARCH LINUX BASE IMAGE ===============]*
# Image pinned to 20260524 snapshot
FROM archlinux:base@sha256:ca64cafd0d2e1fd5744d0f607f11a0b33be173790665c9e2931f756ffbb0a37c AS arch-build

# Arch packages pinned to 20260524 snapshot
RUN echo "Server = https://archive.archlinux.org/repos/2026/05/24/\$repo/os/\$arch" \
    > /etc/pacman.d/mirrorlist

# *=============== DEFINE USERNAME VARIABLE ===============*
ENV DENV_USERNAME=dev

# *=============== ADD ( NON-ROOT ) DEV USER ===============*
RUN useradd --create-home --shell /bin/bash $DENV_USERNAME

# *=============== ACCESS THE CONTAINER AS NON-ROOT USER BY DEFAULT ===============*
USER $DENV_USERNAME
WORKDIR /home/$DENV_USERNAME

# *[=============== SET ALIAS FOR VSCODE BUILD STAGE ===============]*
FROM arch-build AS vdev

# *[=============== SET ALIAS FOR NEOVIM BUILD STAGE ===============]*
FROM vdev AS ndev

USER root

# Add Neovim
RUN pacman -Syu --noconfirm \
  neovim \
  && pacman -Scc --noconfirm

USER $DENV_USERNAME
