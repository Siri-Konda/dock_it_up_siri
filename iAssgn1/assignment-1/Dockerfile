FROM python:3.11-slim

WORKDIR /app
COPY index.html .
COPY me.html .
COPY surprise.html .
COPY web.html .

EXPOSE 8000

CMD ["python", "-m", "http.server", "8000"]
