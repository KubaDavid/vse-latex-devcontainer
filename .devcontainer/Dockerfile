FROM danteev/texlive

# Update apt cache and install required packages
RUN apt-get update && apt-get install -y \
    curl \
    git \
    zsh \
    build-essential \
    libssl-dev \
    libffi-dev && \
    apt-get clean

RUN sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" "" --unattended && \
    sed -i 's/ZSH_THEME=".*"/ZSH_THEME="robbyrussell"/g' ~/.zshrc
