FROM --platform=i386 i386/debian:buster
ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && apt -y upgrade && \
    apt -y install curl git build-essential unzip bash

SHELL ["/bin/bash", "-c"]

RUN mkdir -p /root/.local/share/fonts
RUN cd /root/.local/share/fonts && curl -fLO https://github.com/ryanoasis/nerd-fonts/raw/HEAD/patched-fonts/DroidSansMono/DroidSansMNerdFont-Regular.otf

RUN git clone https://github.com/asdf-vm/asdf.git /root/.asdf --branch v0.14.0
#ENV ASDF_DIR="/root/.asdf/"
RUN alias asdf=/root/.asdf/bin/asdf
RUN bash "/root/.asdf/asdf.sh"
RUN bash "/root/.asdf/completions/asdf.bash"

RUN asdf install kubectl latest
RUN asdf install vault latest
RUN asdf install terraform latest
RUN asdf install packer latest
RUN asdf install vault latest
RUN asdf install packer latest
RUN asdf install terraform latest
RUN asdf install nomad latest
RUN asdf install boundary latest
RUN asdf install consul latest
RUN asdf install helm latest
RUN asdf install awscli latest
RUN asdf global kubectl latest
RUN asdf global vault latest
RUN asdf global packer latest
RUN asdf global terraform latest
RUN asdf global vault latest
RUN asdf global packer latest
RUN asdf global terraform latest
RUN asdf global consul latest
RUN asdf global nomad latest
RUN asdf global boundary latest
RUN asdf global helm latest
RUN asdf global awscli latest

RUN curl -sS https://starship.rs/install.sh | sh
#RUN eval "$(starship init bash)"
#RUN mkdir "/root/.config "&& \
#RUN starship preset pastel-powerline -o ~/.config/starship.toml

COPY ./.bashrc /root/.bashrc