FROM python:3.7-slim

COPY ./docker/images/findhelp-python3.7/requirements.txt /tmp/requirements.txt
RUN python -m pip install -r /tmp/requirements.txt

RUN mkdir /findhelp /findhelp/tests /findhelp/src /findhelp/test_results /findhelp/dist

RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "vim"]

COPY ["./setup.py", "/findhelp"]
COPY ["./README.md", "/findhelp"]
COPY ["./tests/", "/findhelp/tests"]
COPY ["./dist/", "/findhelp/dist"]

WORKDIR /findhelp/dist 
RUN pip install ./findhelp-0.1.0-py3-none-any.whl

CMD tail -f /dev/null

ENV PATH="/usr/local/bin:${PATH}"


