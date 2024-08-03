FROM --platform=i386 i386/debian:buster
ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt -y upgrade && \
    apt -y install curl git unzip bash

SHELL ["/bin/bash", "-c"]
ENV HOME "/root"

RUN mkdir -p ${HOME}/.local/share/fonts
RUN cd ${HOME}/.local/share/fonts && curl -fLO https://github.com/ryanoasis/nerd-fonts/raw/HEAD/patched-fonts/DroidSansMono/DroidSansMNerdFont-Regular.otf

COPY ./.bashrc ${HOME}/.bashrc
RUN . ${HOME}/.bashrc

RUN git clone https://github.com/asdf-vm/asdf.git ${HOME}/.asdf --branch v0.14.0
RUN . "${HOME}/.asdf/asdf.sh"
RUN . "${HOME}/.asdf/completions/asdf.bash"
ENV PATH "${HOME}/.asdf/bin:${PATH}"

RUN asdf plugin-add kubectl https://github.com/asdf-community/asdf-kubectl.git
RUN asdf plugin-add terraform https://github.com/asdf-community/asdf-hashicorp.git
RUN asdf plugin-add helm https://github.com/Antiarchitect/asdf-helm.git
RUN asdf plugin-add kind https://github.com/reegnz/asdf-kind.git
RUN asdf plugin add awscli
RUN asdf install kubectl latest
RUN asdf install terraform latest
RUN asdf install helm latest
RUN asdf install awscli latest
RUN asdf global kubectl latest
RUN asdf global terraform latest
RUN asdf global helm latest
RUN asdf global awscli latest

RUN curl -O https://starship.rs/install.sh && chmod +x install.sh && ./install.sh --yes
RUN eval "$(starship init bash)"
RUN mkdir "${HOME}/.config"
RUN starship preset pastel-powerline -o "${HOME}/.config/starship.toml"
