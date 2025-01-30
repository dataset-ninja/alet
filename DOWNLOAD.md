Dataset **METU-ALET** can be downloaded in [Supervisely format](https://developer.supervisely.com/api-references/supervisely-annotation-json-format):

 [Download](https://assets.supervisely.com/remote/eyJsaW5rIjogImZzOi8vYXNzZXRzLzM1MzJfTUVUVS1BTEVUL21ldHVhbGV0LURhdGFzZXROaW5qYS50YXIiLCAic2lnIjogIjNpT2FsdWJQREVLa2lyaUdvWE1ER0E2djY5OTNZQytHcFhBRGNyaU1ZcEk9In0=)

As an alternative, it can be downloaded with *dataset-tools* package:
``` bash
pip install --upgrade dataset-tools
```

... using following python code:
``` python
import dataset_tools as dtools

dtools.download(dataset='METU-ALET', dst_dir='~/dataset-ninja/')
```
Make sure not to overlook the [python code example](https://developer.supervisely.com/getting-started/python-sdk-tutorials/iterate-over-a-local-project) available on the Supervisely Developer Portal. It will give you a clear idea of how to effortlessly work with the downloaded dataset.

The data in original format can be [downloaded here](https://cengmetuedutr-my.sharepoint.com/:u:/g/personal/skalkan_ceng_metu_edu_tr/Ee9IYWHjbWxMrQNuVkuvlU0Buu3DgplFP7BBAWMyG06Qlw?e=z84zLt).