FROM --platform=i386 i386/debian:buster
ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt -y upgrade && \
    apt -y install curl git build-essential unzip bash

SHELL ["/bin/bash", "-c"]
ENV HOME "/root"
COPY ./.bashrc ${HOME}/.bashrc
RUN . ${HOME}/.bashrc

RUN mkdir -p ${HOME}/.local/share/fonts
RUN cd ${HOME}/.local/share/fonts && curl -fLO https://github.com/ryanoasis/nerd-fonts/raw/HEAD/patched-fonts/DroidSansMono/DroidSansMNerdFont-Regular.otf

RUN git clone https://github.com/asdf-vm/asdf.git ${HOME}/.asdf --branch v0.14.0
RUN . "${HOME}/.asdf/asdf.sh"
RUN . "${HOME}/.asdf/completions/asdf.bash"
ENV PATH "${HOME}/.asdf/bin:${PATH}"

RUN asdf plugin-add kubectl https://github.com/asdf-community/asdf-kubectl.git
RUN asdf plugin-add vault https://github.com/asdf-community/asdf-hashicorp.git
RUN asdf plugin-add terraform https://github.com/asdf-community/asdf-hashicorp.git
RUN asdf plugin-add packer https://github.com/asdf-community/asdf-hashicorp.git
RUN asdf plugin-add nomad https://github.com/asdf-community/asdf-hashicorp.git
RUN asdf plugin-add boundary https://github.com/asdf-community/asdf-hashicorp.git
RUN asdf plugin-add consul https://github.com/asdf-community/asdf-hashicorp.git
RUN asdf plugin-add helm https://github.com/Antiarchitect/asdf-helm.git
RUN asdf plugin-add flux2 https://github.com/tablexi/asdf-flux2.git
RUN asdf plugin-add k9s https://github.com/looztra/asdf-k9s
RUN asdf plugin-add kind https://github.com/reegnz/asdf-kind.git
RUN asdf plugin add awscli
RUN asdf install kubectl latest
RUN asdf install vault latest
RUN asdf install terraform latest
RUN asdf install packer latest
RUN asdf install nomad latest
RUN asdf install boundary latest
RUN asdf install consul latest
RUN asdf install helm latest
RUN asdf install awscli latest
RUN asdf global kubectl latest
RUN asdf global vault latest
RUN asdf global packer latest
RUN asdf global terraform latest
RUN asdf global consul latest
RUN asdf global nomad latest
RUN asdf global boundary latest
RUN asdf global helm latest
RUN asdf global awscli latest

RUN curl -O https://starship.rs/install.sh && chmod +x install.sh && ./install.sh --yes
#RUN eval "$(starship init bash)"
#RUN mkdir "${HOME}/.config
#RUN starship preset pastel-powerline -o ~/.config/starship.toml
