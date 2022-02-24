# Backend developer interview question #2

Docker orchestration that runs a Flask app.

## Installation with Docker compose

Use sh to execute run_docker.sh. 

```bash
sh run_docker.sh
```
The sh file executes the services in the docker-compose.yml file , it includes a container for the Flask app and another for MongoDB.

## Installation with Dockerfile

Move to app folder. Build the container image.

```bash
docker build -t app 
```
Run the container on port 5000.

```bash
docker run -dp 5000:5000 app
```

## TEST
Open Postman and enter the URL:
```
http://127.0.0.1:5000/
```
Postman screenshot:


![home](https://github.com/medinaalonso/DataGran/blob/0cc42d3414b23762ea23c48cd213115e66c45193/Screenshot%20from%202022-02-23%2019-02-59.png)
 
 If the response is a HTML command the installation is successful. 

## New_task

The following URL uses a POST method to publish a JSON to the API and then return the ID

```
http://192.168.1.65:5000/new_task
```

JSON example:
```
{"cmd":"ls"}
```
API response:
```
{
    "id": "6216ce1f168bd6d45a15293a"
}
```


Postman screenshot:


![new_task](https://github.com/medinaalonso/DataGran/blob/0cc42d3414b23762ea23c48cd213115e66c45193/Screenshot%20from%202022-02-23%2019-03-29.png)


## Get_output
The following URL uses a GET method to pass an ID to the API and then return the values for that specific ID.

```
http://192.168.1.65:5000/get_output?id=6216ca77f8a564f13af36cba
```

API response:

```
{
    "output": {
        "cmd": "ls"
    }
}
```

Postman screenshot:


![get_output](https://github.com/medinaalonso/DataGran/blob/0cc42d3414b23762ea23c48cd213115e66c45193/Screenshot%20from%202022-02-23%2019-03-42.png)

