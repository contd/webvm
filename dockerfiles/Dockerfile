FROM --platform=i386 i386/debian:buster
ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt -y upgrade && \
    apt -y install curl git build-essential unzip bash

SHELL ["/bin/bash", "-c"]
COPY ./.bashrc /root/.bashrc
RUN . /root/.bashrc

RUN mkdir -p /root/.local/share/fonts
RUN cd /root/.local/share/fonts && curl -fLO https://github.com/ryanoasis/nerd-fonts/raw/HEAD/patched-fonts/DroidSansMono/DroidSansMNerdFont-Regular.otf

RUN git clone https://github.com/asdf-vm/asdf.git /root/.asdf --branch v0.14.0
RUN . "/root/.asdf/asdf.sh"
RUN . "/root/.asdf/completions/asdf.bash"

RUN /root/.asdf/bin/asdf install kubectl latest
RUN /root/.asdf/bin/asdf install vault latest
RUN /root/.asdf/bin/asdf install terraform latest
RUN /root/.asdf/bin/asdf install packer latest
RUN /root/.asdf/bin/asdf install vault latest
RUN /root/.asdf/bin/asdf install packer latest
RUN /root/.asdf/bin/asdf install terraform latest
RUN /root/.asdf/bin/asdf install nomad latest
RUN /root/.asdf/bin/asdf install boundary latest
RUN /root/.asdf/bin/asdf install consul latest
RUN /root/.asdf/bin/asdf install helm latest
RUN /root/.asdf/bin/asdf install awscli latest
RUN /root/.asdf/bin/asdf global kubectl latest
RUN /root/.asdf/bin/asdf global vault latest
RUN /root/.asdf/bin/asdf global packer latest
RUN /root/.asdf/bin/asdf global terraform latest
RUN /root/.asdf/bin/asdf global vault latest
RUN /root/.asdf/bin/asdf global packer latest
RUN /root/.asdf/bin/asdf global terraform latest
RUN /root/.asdf/bin/asdf global consul latest
RUN /root/.asdf/bin/asdf global nomad latest
RUN /root/.asdf/bin/asdf global boundary latest
RUN /root/.asdf/bin/asdf global helm latest
RUN /root/.asdf/bin/asdf global awscli latest

RUN curl -sS https://starship.rs/install.sh | sh
#RUN eval "$(starship init bash)"
#RUN mkdir "/root/.config "&& \
#RUN starship preset pastel-powerline -o ~/.config/starship.toml
