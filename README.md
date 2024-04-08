# Vegetable Prediction

## Instructions

### Build Docker Image
Build the Docker image for the project:

```bash
docker build -t ca2:latest .
```

### Run Docker Container
Run the Docker container:

```bash
docker run ca2:latest --name bonk-choy
```

### Run Tests
Run tests with the following commands:

For regular tests:

```bash
FLASK_ENV=testing python -m pytest -m "not rpa"
```

For RPA (Robotic Process Automation) tests:

```bash
docker run -d -p 4444:4444 -p 7900:7900 --name selenium-chrome --shm-size=2g selenium/standalone-chrome
```

```bash
docker run -d -p 4444:4444 -p 7900:7900 --name selenium-edge --shm-size=2g selenium/standalone-edge
```

<!-- ```bash
docker run -d -p 4444:4444 -p 7900:7900 --name selenium-firefox --shm-size=2g selenium/standalone-firefox
``` -->

```bash
FLASK_ENV=testing python -m pytest -m rpa --loc=local --browser=chrome
```

```bash
FLASK_ENV=testing python -m pytest -m rpa --loc=local --browser=edge
```

<!-- ```bash
FLASK_ENV=testing python -m pytest -m rpa --loc=local --browser=firefox
``` -->

## Dependencies

```bash
pip install -r requirements.txt
```

## Contributors

- Glenn Wu

## License

This project is licensed under the [MIT License](LICENSE).