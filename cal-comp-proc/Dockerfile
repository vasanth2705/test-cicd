# syntax=docker/dockerfile:1
FROM python:3.10-slim

WORKDIR /app

# Copy only root-level pyproject + lock
COPY /pyproject.toml /uv.lock ./

# Install dependencies with pip (uv could be used too if installed in base image)
RUN pip install uv && uv sync --frozen

# Copy only this service's code
COPY ./cal-comp-proc/src ./src

CMD ["python", "src/main.py"]
