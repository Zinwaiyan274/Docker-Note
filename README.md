# Docker-Note

![Docker_Logo](Docker-Logo_Horizontel_279x131.b8a5c41e56b77706656d61080f6a0217a3ba356d (1).png)


## Create Imgae by DockerFile - Build - Run the container


step 1. create DockerFile
step 2. nano DockerFile

```
 
FROM python:bookworm

 

WORKDIR /app

 

# Install dependencies

RUN apt-get update && apt-get install -y \
    libglib2.0-0 \
    libsm6 \
    libxext6 \
    libxrender-dev \
    libgl1-mesa-dev \
    && rm -rf /var/lib/apt/lists/*

 

COPY requirements.txt .

 

RUN pip install -r requirements.txt

 

COPY . .

 

CMD ["python", "test.py"]
```



step 3.  

```
docker build -t my-python-app -f DockerFile .
```

Step 4.


```
docker run --name my-container my-python-app

```
</br>
</br>



## Pull and Push the docker 

</br>


### To Pull

```
docker pull repo_username/repo_name:tagname
```

### To Push


Step1. Tag first

```
docker tag image_name:latest waii274/repo_name:latest
```

Step2. Then, Push

```
docker push waii274/repo_name:latest
```



