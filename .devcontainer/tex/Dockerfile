FROM alpine

RUN apk update && apk add texmf-dist texlive-full make python3 biber

# Install pygments
RUN python -m ensurepip --upgrade
RUN pip3 install pygments


# Install pgfgantt
RUN wget https://mirrors.ctan.org/graphics/pgf/contrib/pgfgantt.zip && \
    unzip pgfgantt.zip
WORKDIR /pgfgantt
RUN latex pgfgantt.ins && \
    mkdir -p ~/texmf/tex/latex/pdfgantt/ && \
    cp pgfgantt.sty ~/texmf/tex/latex/pdfgantt/
    
# Cleanup
WORKDIR /
RUN rm -r pgfgantt pgfgantt.zip

RUN apk add git
