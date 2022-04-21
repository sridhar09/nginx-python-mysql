FROM python:3.7

WORKDIR /src
COPY ./server.py /src/server.py
COPY ./requirements.txt /src/requirements.txt
RUN pip install -r requirements.txt --no-cache-dir
RUN chmod +x ./server.py
CMD ["/src/server.py"]