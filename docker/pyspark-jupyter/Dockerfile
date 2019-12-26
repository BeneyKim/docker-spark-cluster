FROM bhkim81/spark-base:latest

ENV TINI_VERSION v0.6.0
ENV PYSPARK_DRIVER_PYTHON=jupyter
ENV PYSPARK_DRIVER_PYTHON_OPTS='notebook'

ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /usr/bin/tini
RUN chmod +x /usr/bin/tini
ENTRYPOINT ["/usr/bin/tini", "--"]

COPY run-jupyter-nootbook.sh /
RUN pip3 install jupyter findspark

EXPOSE 8888
# CMD ["jupyter", "notebook", "--port=8888", "--no-browser", "--ip=0.0.0.0"]
CMD ["/bin/bash", "/run-jupyter-nootbook.sh"]
