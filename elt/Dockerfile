FROM python:3.12-slim
# Set the working directory
WORKDIR .

RUN apt-get update && apt-get install -y postgresql \
    postgresql-client \
    libpq-dev \
    gcc \
    python3-dev \
    build-essential \
    && rm -rf /var/lib/apt/lists/*
#    postgresql-dev \
    
# Install PostgreSQL client for macOS (via Homebrew)
#RUN sudo apt-get update && sudo apt-get install -y curl && \
#    curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh | bash && \
 #   brew install libpq && \
 #   ln -s /usr/local/opt/libpq/bin/psql /usr/local/bin/psql
COPY ./requirements.txt .
COPY elt_script.py .

RUN pip install -r requirements.txt

CMD ["python", "elt_script.py"]