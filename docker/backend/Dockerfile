# Start from the official Python base image.
FROM arm64v8/python:3.9

# Set the current working directory to /code.
WORKDIR /code

# Copy the file with the requirements to the /code directory.
COPY ./app/requirements.txt /code/requirements.txt

# Install the package dependencies in the requirements file.
RUN pip install --no-cache-dir --upgrade -r /code/requirements.txt

# Copy the ./app directory inside the /code directory.
COPY ./app /code/app

# RUN apt-get update && apt-get -y install fontconfig libxext6 libxrender1 xfonts-utils \
#      libfontenc1 x11-common xfonts-75dpi xfonts-base \
#      fonts-wqy-microhei ttf-wqy-microhei fonts-wqy-zenhei ttf-wqy-zenhei \
#      ghostscript \
#  && curl -L -o /tmp/wkhtmltopdf.deb https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6.1-3/wkhtmltox_0.12.6.1-3.bookworm_arm64.deb \
#  && dpkg -i --force-depends /tmp/wkhtmltopdf.deb \
#  && fc-cache -f -v  

# Set the command to run the uvicorn server.
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "5000"]
