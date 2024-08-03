FROM --platform=i386 i386/debian:buster
ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt -y upgrade && \
    apt -y install curl git build-essential unzip

RUN mkdir -p $HOME/.local/share/fonts
RUN cd $HOME/.local/share/fonts && curl -fLO https://github.com/ryanoasis/nerd-fonts/raw/HEAD/patched-fonts/DroidSansMono/DroidSansMNerdFont-Regular.otf

RUN git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.14.0
RUN . "$HOME/.asdf/asdf.sh"
RUN . "$HOME/.asdf/completions/asdf.bash"

RUN asdf install kubectl latest && \
    asdf install vault latest && \
    asdf install terraform latest && \
    asdf install packer latest && \
    asdf install vault latest && \
    asdf install packer latest && \
    asdf install terraform latest && \
    asdf install nomad latest && \
    asdf install boundary latest && \
    asdf install consul latest && \
    asdf install helm latest && \
    asdf install awscli latest && \
    asdf global kubectl latest && \
    asdf global vault latest && \
    asdf global packer latest && \
    asdf global terraform latest && \
    asdf global vault latest && \
    asdf global packer latest && \
    asdf global terraform latest && \
    asdf global consul latest && \
    asdf global nomad latest && \
    asdf global boundary latest && \
    asdf global helm latest && \
    asdf global awscli latest

RUN curl -sS https://starship.rs/install.sh | sh
    # eval "$(starship init bash)" && \
    # mkdir "$HOME/.config "&& \
    # starship preset pastel-powerline -o ~/.config/starship.toml

COPY ./.bashrc /root/.bashrc