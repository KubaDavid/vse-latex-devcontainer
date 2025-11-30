FROM danteev/texlive

ARG USERNAME=vse
ARG USER_UID=1000
ARG USER_GID=1000

# Update apt cache and install required packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    git \
    zsh \
    fzf \
    nano \
    sudo \
    ca-certificates \
    gnupg \
    build-essential \
    libssl-dev \
    libffi-dev && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Node.js 22 LTS
RUN curl -fsSL https://deb.nodesource.com/setup_22.x | bash - && \
    apt-get install -y nodejs && \
    apt-get clean && rm -rf /var/lib/apt/lists/*

# Rename texlive user to vse (keeps uid 1000, inherits all file ownership)
RUN usermod -l $USERNAME texlive && \
    usermod -d /home/$USERNAME -m $USERNAME && \
    groupmod -n $USERNAME texlive && \
    echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers && \
    chsh -s /bin/zsh $USERNAME

# Persist command history
RUN mkdir -p /commandhistory && \
    touch /commandhistory/.zsh_history && \
    chown -R $USERNAME:$USERNAME /commandhistory

# Create config directories
RUN mkdir -p /home/$USERNAME/.claude && \
    chown -R $USERNAME:$USERNAME /home/$USERNAME/.claude

# Install Task CLI
RUN sh -c "$(curl --location https://taskfile.dev/install.sh)" -- -d -b /usr/local/bin

# Install Claude Code globally via npm
RUN npm install -g @anthropic-ai/claude-code

# Set zsh as default shell
ENV SHELL=/bin/zsh

# Switch to vse user
USER $USERNAME
WORKDIR /home/$USERNAME

# Install zsh-in-docker for nice prompt
ARG ZSH_IN_DOCKER_VERSION=1.2.0
RUN sh -c "$(wget -O- https://github.com/deluan/zsh-in-docker/releases/download/v${ZSH_IN_DOCKER_VERSION}/zsh-in-docker.sh)" -- \
    -p git \
    -p fzf \
    -x
