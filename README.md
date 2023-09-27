# Docker-Note

![Docker_Logo](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHcAAABPCAMAAADmzqp4AAAAeFBMVEX////5+fkdY+0AS+sAVuwOXu1/nfP8/f8AVOwAW+wAWezz9v4AUOsARusATesVYO2Io/NTf/DV3/u/zfi3x/hylPJKe++lufZIeO9Xg/Crv/cAQ+vF0/rn7Pzg5/ydtPWTrPQnaO1pjvHM2Po5bu5nh/A/c+4APur2FYG0AAACuElEQVRoge3a626kIBQAYBYQEVDw7jjeb/P+b7hHZzrbbW1q0nYmTTiJxgD6CR6Pf0TI/fP4cBGw6PEB8DNYgK1rXeta17rWta51rWtd6/56t0ni8RluTnj4FFeJ0zPcsevKR7pyyopxyeY4PJmHukTTSumlpN5tncfZfYR7FiomYioVveVVSL8zwXbdKIpkXFWwjXVVRXUU1agWmCevB8V453JldnBRdt0zP1dnTmKf9yVRMyOEoYZjHbZdfL9ud5bvzzTeTuNhN9CqCjSvlDOV3BuMoAZJD2MtPF7cXX/Pdb7ipixtrpsZU5YnjMEKzxpDqOtaS4nazXXlywJI+c/ddrcuuR4dcKM5ZYy93tYYCmA9Stt1SLkIbAyBq3UTnbYmmWK6lFe3nnsXSdPTJYdCK5IUi6L+1E24dnYCWN0m240b0puZaCVRSApT+PCiSUxmgy9VB27p+B1ye/9kesiLkQo1MBx96sYU74fDrgNGksK+EsrNyTrXluRoCNavR+ka3ZzI1CDEeLXdYTVS3bx/kjtuoz5w+e0psWA7SIkM+61hylwnvfYZ7YntEBdjDEHTSLU77I4rnQ/Yl/OH64sLeTVdtRnLIL+5IusxzE9qx19DhVEQH3NRugt7w0v/llCgBSjU64Hbh66+9RrPremaW3hpoPo0kRwPuyPfY4t7wWhUCBfOA4YSsj5y5ieIEXi/ZCfXfB755KJOrSvQ1ui4iwbvHUtf17/Ox3NBFmgZyDRMPqy27FU268u41auEzAjBgKG/JJCFh113egM7tPtvQBU6U7vdSFl4xVZJIJNFVsGbvTa3MGGUL94JyJrvpfN+vZIz13dUCzHsnvql+OA7GIcBFZ4nBFdZ+7bW/KALc47zrs2T6GCd/zb3h8O61rWuda1rXeta17rWte5vcJ/1f86T/kf6C0umLcKjVSLgAAAAAElFTkSuQmCC)


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



