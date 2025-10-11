FROM selenium/standalone-chrome

USER root
RUN apt-get update && \
    apt-get install -y --no-install-recommends python3-pip && \
    rm -rf /var/lib/apt/lists/*

COPY ./requirements.txt /adminbot/requirements.txt
RUN python3 -m pip install --no-cache-dir -r /adminbot/requirements.txt

COPY . /adminbot
RUN chown -R seluser:seluser /adminbot
USER seluser
WORKDIR /adminbot

CMD ["python3", "/adminbot/main.py"]