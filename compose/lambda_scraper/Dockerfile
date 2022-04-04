FROM public.ecr.aws/lambda/python:3.9

RUN pip install --upgrade pip

RUN pip install psycopg2-binary

# setting workdir so we coppy all relevant files into it
WORKDIR ${LAMBDA_TASK_ROOT}

COPY ./requirements/base.txt .
RUN pip --no-cache-dir install -r base.txt

COPY ./requirements/extended.txt .
RUN pip --no-cache-dir install -r extended.txt

ADD app .

CMD [ "main.handler" ]
