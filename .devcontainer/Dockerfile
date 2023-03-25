FROM ubuntu:latest

# non interactive frontend for locales
ENV DEBIAN_FRONTEND=noninteractive

# installing texlive and utils
RUN apt-get update
RUN apt-get -y install --no-install-recommends pandoc texlive texlive-latex-extra texlive-extra-utils texlive-fonts-extra texlive-bibtex-extra biber latexmk make git procps locales curl
RUN apt-get -y install texlive-lang-cyrillic
RUN apt-get -y install texlive-xetex

# generating locales
RUN sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen && \
    dpkg-reconfigure --frontend=noninteractive locales && \
    update-locale LANG=en_US.UTF-8
ENV LANGUAGE=en_US.UTF-8 LANG=en_US.UTF-8 LC_ALL=en_US.UTF-8


# installing cpanm & missing latexindent dependencies
RUN curl -L http://cpanmin.us | perl - --self-upgrade && \
    cpanm Log::Dispatch::File YAML::Tiny File::HomeDir

# Times New Roman

RUN apt install fontconfig
COPY ./TimesNewRoman.ttf ./TimesNewRoman.ttf
RUN cp ./TimesNewRoman.ttf /usr/local/share/fonts/TimesNewRoman.ttf
RUN fc-cache -fv

# Pigments 
RUN apt-get install -y python3 python3-pip
RUN pip3 install pygments