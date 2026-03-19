FROM python:3.12-slim

RUN pip install --no-cache-dir uv

WORKDIR /app

COPY src/requirements.txt ./requirements.txt

RUN uv pip install --system --no-cache -r requirements.txt

COPY src/ ./src

CMD ["uv", "run", "gunicorn", "-b", "0.0.0.0:5001", "src.app:app"]
