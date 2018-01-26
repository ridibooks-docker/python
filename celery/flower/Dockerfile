FROM python:3

RUN pip install redis flower

ENV BROKER_URL=redis://redis:6379/1
ENV ADDRESS=0.0.0.0
ENV PORT=5555

EXPOSE $PORT

CMD celery flower --address=$ADDRESS --port=$PORT --broker=$BROKER_URL
