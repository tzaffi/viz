FROM python:3.7
ENV PATH="/app/.local/bin/:${PATH}"

COPY viz/ /app
COPY data/ /app/data

WORKDIR /app
RUN pip install --upgrade pip && \
    pip install --no-cache-dir -r requirements.txt


EXPOSE 8888

CMD ["jupyter", "notebook", "--ip='*'", "--port=8888", "--no-browser", "--allow-root"]
