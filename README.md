# BYOR

## Docker image with a CSV/JSON file from the host machine
You can check your setup by clicking on "Build my radar" and by loading the csv/json file from these locations:

http://localhost:8080/files/radar.csv
http://localhost:8080/files/radar.json

```bash
docker pull wwwthoughtworks/build-your-own-radar
docker run --rm -p 8080:80 -e SERVER_NAMES="localhost 127.0.0.1" -v $PWD/data/:/opt/build-your-own-radar/files wwwthoughtworks/build-your-own-radar:latest
open http://localhost:8080
```
This will:

* Spawn a server that will listen locally on port `8080`.
* Mount the host volume on the relative `./data/`  (providing you are executing the commands from the root of this project) into the container on `/opt/build-your-own-radar/files/`.
* Open http://localhost:8080 and for the URL enter: `http://localhost:8080/files/<NAME_OF_YOUR_FILE>.<EXTENSION_OF_YOUR_FILE[csv/json]>`. It needs to be a csv/json file.
You can now work locally on your machine, updating the csv/json file and render the result back on your browser.

For the example radar open http://localhost:8080/?documentId=http%3A%2F%2Flocalhost%3A8080%2Ffiles%2FexampleRadar.csv

You should get something that looks like this!
![Rendered tech radar after inserting the URL of the file](/_images/exampleRader.png)
