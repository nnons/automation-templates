FROM python:3

RUN python -m pip install --upgrade pip
RUN git clone https://github.com/ProjectAnte/dnsgen
WORKDIR /dnsgen

RUN pip3 install -r requirements.txt
RUN python3 setup.py install

ENTRYPOINT [ "dnsgen" ]