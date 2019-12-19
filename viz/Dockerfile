FROM continuumio/miniconda3
RUN conda install jupyter -y --quiet

ENV PATH="/opt/conda/bin:${PATH}"
COPY . /opt/viz
RUN mkdir /opt/notebooks

RUN mkdir  ~/.aws ~/.ssh && \
	ln -s /run/secrets/aws_config ~/.aws/config && \
	ln -s /run/secrets/aws_creds ~/.aws/credentials && \
	ln -s /run/secrets/ssh_key ~/.ssh/id_rsa

RUN apt-get update && \
	apt-get install -y gcc && \
	apt-get install -y libpq-dev

RUN conda install pandas=0.25.1 numpy scipy boto3 ipython

RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r /opt/viz/viz/requirements.txt

EXPOSE 8888

CMD ["jupyter", "notebook", "--notebook-dir=/opt/notebooks", "--ip='*'", "--port=8888",  "--no-browser", "--allow-root", "--NotebookApp.iopub_data_rate_limit=10000000"]
