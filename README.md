# Docker images with Azure Machine Learning service Python SDK

This is an **unofficial** repository hosting Docker images that has Azure Machine Learning service Python SDK installed. The purpose is to enable users to quickly try the SDK by launching a Docker container. I work in the Azure Machine Learning team as a Program Manager, and I intend to offer my best effort personal support to these images. However, I want to be super clear that these are NOT officially supported by Microsoft.

\- Hai Ning (Principal Program Manager, Azure Machine Learning, Microsoft)

## Quick start
To try the latest SDK, simply type:
```sh
docker run -it -p 8887:8887 ninghai/azureml
```
Then launch a browser session, navigate to `https://localhost:8887`, and open the `configuration.ipynb` notebook.

## Additional SDK components
Please note in order to keep the image size small, I have only installed the core SDK in the image, which is the equivalent of running `pip install azureml-sdk[notebooks]`. If you need additional SDK components, you will need to install them in the `azureml` conda environment inside the Docker image. For example:

```sh
# install dataprep components
pip install azureml-dataprep

# install the core SDK and automated ml components
pip install azureml-sdk[automl]

# install the core SDK and model explainability component
pip install azureml-sdk[explain]

# install the core SDK and experimental components
pip install azureml-sdk[contrib]
```

## Try a specific version of the SDK
To try a specific version of the SDK, add the version number as the image tag:
```sh
docker run -it -p 8887:8887 ninghai/azureml:<version_number>
```
## Supported SDK versions
**December 21, 2018 release**:
```sh
docker run -it -p 8887:8887 ninghai/azureml:1.0.6
```

**December 3rd, 2018 GA release**:
```sh
docker run -it -p 8887:8887 ninghai/azureml:1.0.2
```
## Links
- The source Dockerfiles are hosted in [this directory](./Dockerfiles).
- These Docker images are hosted in [DockerHub](https://cloud.docker.com/u/ninghai/repository/docker/ninghai/azureml).
- Azure Machine Learning service [Documentation Site](https://aka.ms/aml-docs)
- Azure Machine Learning service [sample notebooks repository](https://github.com/Azure/MachineLearningNotebooks)
