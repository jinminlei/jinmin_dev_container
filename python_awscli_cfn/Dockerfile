FROM python:3.8

# Install AWS CLI
RUN pip install awscli --upgrade --user

# Adding AWS CLI Executable to Path
RUN echo 'export PATH=~/.local/bin:$PATH'>>root/.bashrc

# Install groff to enable AWS CLI command line help
RUN apt-get update \
    && apt-get --assume-yes install groff

COPY ./requirements.txt .
COPY ./tools.sh .

# Install pytho project dependencies 
RUN pip install -r requirements.txt
# Install tools needed
RUN /tools.sh