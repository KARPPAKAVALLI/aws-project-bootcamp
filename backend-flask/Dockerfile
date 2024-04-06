#this refers another docker file
FROM python:3.10-slim-buster 

#Make a new Folder Inside the Container
WORKDIR /backend-flask

#Copy from: Inside Container(IC) -> Outside Container(OC)
#this contains all the lib v need to install to run our app 
COPY requirements.txt requirements.txt

#IC
#Install the python lib used for the app
RUN pip3 install -r requirements.txt


# . means EVERYTHING
# first . -> /backend-flask(OC)
#second . -> /backend-flask(IC)
#OC -> IC
COPY . .

#Set Env Varia
#IC & will reamin set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}
#Command to run our app
# --host=0.0.0.0 => means everywhere, -m flask => to run module flask
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]