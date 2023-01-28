FROM python:3

WORKDIR /app

RUN pip install --upgrade pip

# Copy model requirements
COPY requirements.txt .
RUN pip install -r ./requirements.txt

# RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
# RUN bash Miniconda3-latest-Linux-x86_64.sh -b -p $HOME/miniconda
# RUN rm -f Miniconda3-latest-Linux-x86_64.sh

# Copy code and model
COPY . .

EXPOSE 5000

CMD gunicorn -b 0.0.0.0:5000 service --timeout 300 --workers=2 --threads=4 --worker-class=gthread

