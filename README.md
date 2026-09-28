# Causilo Cookbook

Runnable examples for Causilo, a tabular foundation model for classification
and regression.

[`aws-sagemaker/causilo-sagemaker.ipynb`](aws-sagemaker/causilo-sagemaker.ipynb)
deploys Causilo from AWS Marketplace on Amazon SageMaker: a real-time
endpoint, a batch transform job, and clean-up. It runs in SageMaker Studio or
a SageMaker notebook instance.
[`sample-input.parquet`](aws-sagemaker/sample-input.parquet) and
[`sample-output.json`](aws-sagemaker/sample-output.json) are its
classification request and response. The breast cancer data only
demonstrates the request format; Causilo is not intended for medical
diagnosis.

- Documentation: https://docs.nums.world/reference (hosted API; SageMaker limits are in the notebook)
- Technical report: https://arxiv.org/abs/2609.22866
- Support: api@nums.world

## License

The code in this repository is licensed under the Apache License 2.0, except
`aws-sagemaker/sample-input.parquet` (see below). `sample-output.json` is
example output released by Nums AI under the same license; outputs you
generate yourself remain under the Causilo License.

The Causilo model is licensed separately under the
[Causilo License v1.0](https://huggingface.co/nums-ai/causilo/blob/2edc3d8e84149271ab9d87c61be2b4860dc3a938/LICENSE):
non-commercial research, testing and evaluation. Commercial or production use
of Causilo or its outputs, or offering it as a hosted or API service, paid or
free, needs a separate license from Nums AI Inc. (api@nums.world).

`aws-sagemaker/sample-input.parquet` contains the Breast Cancer Wisconsin
(Diagnostic) dataset: Wolberg, W., Mangasarian, O., Street, N. and Street, W.
(1993), UCI Machine Learning Repository, https://doi.org/10.24432/C5DW2B,
licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). It
was taken from scikit-learn's copy (ID column dropped, columns renamed) and
changed: diagnosis mapped to `malignant`/`benign` as `target`, rows shuffled,
the label removed from 100 rows, and request parameters added to the file
metadata.
