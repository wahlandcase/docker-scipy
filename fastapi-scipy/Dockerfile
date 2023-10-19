FROM tiangolo/uvicorn-gunicorn-fastapi:python3.7-alpine3.8

ENV PYTHONUNBUFFERED=1

RUN apk add --no-cache --virtual .build-deps \
 && apk del .build-deps
RUN apk --update add --virtual scipy-runtime gcc musl-dev \
    && apk add --virtual scipy-build \
        build-base python3-dev zlib-dev freetype-dev lcms2-dev tk-dev tcl-dev libzmq openblas-dev freetype-dev pkgconfig gfortran linux-headers zeromq-dev \
    && ln -s /usr/include/locale.h /usr/include/xlocale.h \
    && pip3 install --no-cache-dir numpy==1.17.2 \ 
    && pip3 install --no-cache-dir matplotlib \
    && pip3 install --no-cache-dir scipy==1.3.1 \
    && pip3 install --no-cache-dir cython==0.29.32 \
    && pip3 install --no-cache-dir pyzmq==18.1.0 \
    && pip3 install --no-cache-dir pandas==0.25.1 \
    && pip3 install --no-cache-dir scikit-learn==1.1.1 \
    && pip3 install --no-cache-dir "grpcio>=1.0,<2.0" \
    && pip3 install --no-cache-dir "redislite>=6.2.805324,<7.0" \
    && apk add --virtual scipy-runtime3 \
        freetype libgfortran libgcc libstdc++ musl openblas tcl tk \
    && rm -rf /var/cache/apk/*