# We’ll start by specifying our base image, using the FROM keyword:
FROM alpine:edge

# The next step usually is to write the commands of copying the files and installing the dependencies.
# But first we will install the Python pip package to the alpine linux distribution.
# This will not just install the pip package but any other dependencies too,
# which includes the python interpreter. Add the following RUN command next:
RUN apk add --update py2-pip

# Let’s add the files that make up the Flask Application.
# Install all Python requirements for our app to run. This will be accomplished by adding the lines:
COPY requirements.txt /usr/src/app/
RUN pip install --no-cache-dir -r /usr/src/app/requirements.txt

# Copy the files you have created earlier into our image by using COPY command.
COPY app.py /usr/src/app/
COPY templates/index.html /usr/src/app/templates/

# Specify the port number which needs to be exposed. Since our flask app is running on 5000 that’s what we’ll expose.
EXPOSE 5000

# The last step is the command for running the application which is simply - python ./app.py. Use the CMD command to do that:
# The primary purpose of CMD is to tell the container which command it should run by default when it is started.
CMD ["python", "/usr/src/app/app.py"]
