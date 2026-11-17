# SageMaker inference through Lambda

The notebook splits data, uploads records to S3 and deploys XGBoost to SageMaker. Lambda converts four fields into a CSV row and calls the endpoint. Use a SageMaker environment with the v2 SDK, an execution role and an existing bucket. Upload the included penguin dataset as dataset.csv in that bucket. Set SAGEMAKER_BUCKET for the notebook and SAGEMAKER_ENDPOINT for Lambda. Configure API Gateway separately and delete the endpoint after use to stop ongoing charges.

## Inference request

```mermaid
flowchart LR
    client["Application or Postman"] --> gateway["Amazon API Gateway"]
    gateway --> handler["AWS Lambda: format four fields as CSV"]
    handler --> model["Amazon SageMaker: XGBoost endpoint"]
```

## Run locally

```sh
jupyter notebook ClassificacaoSageMaker.ipynb
```
