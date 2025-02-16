FROM mcr.microsoft.com/devcontainers/base:alpine

ARG USERNAME=user
ARG USER_UID=1000
ARG USER_GID=$USER_UID
ARG PACKAGES="libc6-compat gcompat curl python3 alpine-sdk git xsel py3-pynvim ripgrep lua fzf neovim tmux exa nodejs npm texlive-full"

RUN usermod -l $USERNAME vscode && \
    usermod -d /home/$USERNAME -m $USERNAME && \
    chown -R $USERNAME: /home/$USERNAME && \
    apk update && \
    apk add sudo && \
    echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME && \
    chmod 0440 /etc/sudoers.d/$USERNAME && \
    apk update && \
    apk upgrade && \
    apk add $PACKAGES && \
    curl -s https://ohmyposh.dev/install.sh | bash -s -- -d /usr/local/bin && \
    mkdir -p /tmux/plugins && \
    chown 1000:1000 -R /tmux

USER 1000
RUN export TMUX_PLUGIN_MANAGER_PATH="/tmux/plugins" && \
    git clone https://github.com/tmux-plugins/tpm /tmux/plugins/tpm && \
    /bin/bash /tmux/plugins/tpm/scripts/install_plugins.sh

USER $USERNAME
