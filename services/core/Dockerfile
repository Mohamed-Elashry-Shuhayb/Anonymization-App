FROM python:3.7

RUN pip install fastapi uvicorn spacy
RUN python -m spacy download en_core_web_sm
RUN python -m spacy download fr_core_news_sm

COPY . /api/api

ENV PYTHONPATH=/api
WORKDIR /api

EXPOSE 8000

ENTRYPOINT ["uvicorn"]
CMD ["api.main:app", "--host", "0.0.0.0"]