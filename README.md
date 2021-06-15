# Sample Jupyter Notebooks

This repository contains sample notebooks showcasing how to use the LUSID SDK. You can find a list of the notebooks at [examples/README](examples/README.md).

![LUSID_by_Finbourne](https://content.finbourne.com/LUSID_repo.png)

| branch | status |
| --- | --- |
| `master`  | ![Daily build](https://github.com/finbourne/sample-notebooks/workflows/Daily%20build/badge.svg) ![Build and test](https://github.com/finbourne/sample-notebooks/workflows/Build%20and%20test/badge.svg) |
| `develop` | ![run-sample-notebooks-tests](https://github.com/finbourne/sample-notebooks/workflows/run-sample-notebooks-tests/badge.svg?branch=develop) |



## Running the notebooks locally

You can run the notebooks locally by following these steps:

1. Clone this repository

```
git clone git@github.com:finbourne/sample-notebooks.git
cd sample-notebooks
```

2. Create a `secrets.json` file in the **examples** folder with your LUSID credentials. For more details on this, see the [Using a secrets.json file](https://support.lusid.com/getting-started-with-apis-sdks) documentation.

3. Build the Docker image locally

```
docker build -t finbourne/lusid-sample-notebooks .
```

4. Run the Docker image

**Windows**
```bash
docker run --rm -it --name fbn-jupyter -v %cd%:/home/jovyan -e FBN_SECRETS_PATH=/home/jovyan/examples/secrets.json -p 8888:8888 finbourne/lusid-sample-notebooks
```
**macOS/linux**
```bash
docker run --rm -it --name fbn-jupyter -v $(pwd):/home/jovyan -e FBN_SECRETS_PATH=/home/jovyan/examples/secrets.json -p 8888:8888 finbourne/lusid-sample-notebooks
```

5. Click on the link shown in the console to open up JupyterHub in a browser.
6. You can now navigate to your chosen notebook and run it.
