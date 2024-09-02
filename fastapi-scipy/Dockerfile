FROM tiangolo/uvicorn-gunicorn-fastapi:python3.8-slim

ENV PYTHONUNBUFFERED=1

RUN apt-get update && apt-get install -y gcc g++

RUN pip3 install --no-cache-dir numpy==1.21.5 \ 
    && pip3 install --no-cache-dir cython==0.29.32 \
    && pip3 install --no-cache-dir scikit-learn==0.21.3 \
    && pip3 install --no-cache-dir pyzmq==18.1.0 \
    && pip3 install --no-cache-dir pandas==1.5.3 \
    && pip3 install --no-cache-dir "grpcio>=1.0,<2.0" \
    && pip3 install --no-cache-dir "redislite>=6.2.805324,<7.0" \