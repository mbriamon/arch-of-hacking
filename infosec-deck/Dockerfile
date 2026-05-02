FROM debian:bookworm-slim

# Install dependencies
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    python3-yaml \
    python3-shortuuid \
    vim-latexsuite \
    pandoc \
    python3-shortuuid \
    texlive-latex-base \
    texlive-latex-extra \
    texlive-fonts-recommended \
    texlive-fonts-extra \
    texlive-xetex \
    texlive-extra-utils \
    pcre2-utils \
    imagemagick \
    pdftk \
    qrencode \
    make \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
# Don't do this at home 8-)
RUN pip3 install --no-cache-dir --break-system-packages \
    Cheetah3 \
    pycurl \
    unidecode \
    PyYAML

# Set working dir
WORKDIR /app
COPY . /app
RUN chmod +x bin/*

# Build the deck
RUN make all

# Port for web server
EXPOSE 8000

# Serve the output directory with PDF files for the deck 
CMD ["python3", "-m", "http.server", "8000", "--directory", "out/pdf/en"]