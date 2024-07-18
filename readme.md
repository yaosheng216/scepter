<h1 align="center">🪄SCEPTER</h1>

<p align="center">
<img src="https://img.shields.io/badge/python-%E2%89%A53.8-5be.svg">
<img src="https://img.shields.io/badge/pytorch-%E2%89%A51.12%20%7C%20%E2%89%A52.0-orange.svg">
<a href="https://pypi.org/project/scepter/"><img src="https://badge.fury.io/py/scepter.svg"></a>
<a href="https://github.com/modelscope/scepter/blob/main/LICENSE"><img src="https://img.shields.io/github/license/modelscope/scepter"></a>
<a href="https://github.com/modelscope/scepter/"><img src="https://img.shields.io/badge/scepter-Build from source-6FEBB9.svg"></a>
</p>

🪄SCEPTER is an open-source code repository dedicated to generative training, fine-tuning, and inference, encompassing a suite of downstream tasks such as image generation, transfer, editing.
SCEPTER integrates popular community-driven implementations as well as proprietary methods by Tongyi Lab of Alibaba Group, offering a comprehensive toolkit for researchers and practitioners in the field of AIGC. This versatile library is designed to facilitate innovation and accelerate development in the rapidly evolving domain of generative models.

SCEPTER offers 3 core components:
- [Generative training and inference framework](#tutorials)
- [Easy implementation of popular approaches](#currently-supported-approaches)
- [Interactive user interface: SCEPTER Studio](#launch)


## 🎉 News
- [2024.07]: Support the inference and training of open-source generative models based on the [DiT](https://arxiv.org/abs/2212.09748) architecture, such as [SD3](https://arxiv.org/pdf/2403.03206) and [PixArt](https://arxiv.org/abs/2310.00426).
- [2024.05]: Introducing SCEPTER v1, supporting customized image edit tasks! Simply provide 10 image pairs, SCEPTER will tune an edit tuner for your own Image-to-Image tasks, like `Clay Style`, `De-Text`, `Segmentation`, etc.
- [2024.04]: New [StyleBooth](https://ali-vilab.github.io/stylebooth-page/) demo on SCEPTER Studio for`Text-Based Style Editing`.
- [2024.03]: We optimize the training UI and checkpoint management. New [LAR-Gen](https://arxiv.org/abs/2403.19534) model has been added on SCEPTER Studio, supporting `zoom-out`, `virtual try on`, `inpainting`.
- [2024.02]: We release new SCEdit controllable image synthesis models for SD v2.1 and SD XL. Multiple strategies applied to accelerate inference time for SCEPTER Studio.
- [2024.01]: We release **SCEPTER Studio**, an integrated toolkit for data management, model training and inference based on [Gradio](https://www.gradio.app/).
- [2024.01]: [SCEdit](https://arxiv.org/abs/2312.11392) support controllable image synthesis for training and inference.
- [2023.12]: We propose [SCEdit](https://arxiv.org/abs/2312.11392), an efficient and controllable generation framework.
- [2023.12]: We release [🪄SCEPTER](https://github.com/modelscope/scepter/) library.


## 🖼 Gallery for Recent Works

### Edit Tuners

Simply provide 10 image pairs, SCEPTER will tune an edit tuner for your own Image-to-Image tasks, like `Clay Style`, `De-Text`, `Segmentation`, etc.
Try our official few-shot datasets: [De-Text](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=datasets%2Fdetext.zip), [Image2Hed](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=datasets%2Fhed_pair.zip), [Image2Depth](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=datasets%2Fimage2depth.zip), [Depth2Image](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=datasets%2Fdepth2image.zip).


<table><tbody>
  <tr>
    <th align="center" colspan="4">Clay Style<br>Prompt: "Convert this image into clay style"</th>
  </tr>
  <tr>
    <td><img src="asset/images/edit_tuner/vermeer.jpeg" width="300"></td>
    <td><img src="asset/images/edit_tuner/clay_vermeer.jpeg" width="300"></td>
    <td><img src="asset/images/edit_tuner/cat_512.jpg" width="300"></td>
    <td><img src="asset/images/edit_tuner/clay_cat.jpeg" width="300"></td>
  </tr>
  <tr>
    <th align="center" colspan="2">De-Text<br>Prompt: "Remove the texts"</th>
    <th align="center" colspan="2">Image2Hed<br>Prompt: "Convert to an edge map"</th>
  </tr>
  <tr>
    <td><img src="asset/images/edit_tuner/text.jpg" width="300"></td>
    <td><img src="asset/images/edit_tuner/detext.jpeg" width="300"></td>
    <td><img src="asset/images/edit_tuner/cat_512.jpg" width="300"></td>
    <td><img src="asset/images/edit_tuner/hed.jpeg" width="300"></td>
  </tr>
    <tr>
    <th align="center" colspan="2">Image2Depth<br>Prompt: "Calculate the depth map"</th>
    <th align="center" colspan="2">Depth2Image<br>Prompt: "Convert depth map into color image"</th>
  </tr>
  <tr>
    <td><img src="asset/images/edit_tuner/house.jpg" width="300"></td>
    <td><img src="asset/images/edit_tuner/image2depth.jpeg" width="300"></td>
    <td><img src="asset/images/edit_tuner/depth.jpg" width="300"></td>
    <td><img src="asset/images/edit_tuner/depth2image.jpeg" width="300"></td>
  </tr>
</tbody>
</table>
Note: Left image is input and right image is output.

## 🛠️ Installation

- Create new environment with `conda` command:

```shell
conda env create -f environment.yaml
conda activate scepter
```

- Install with `pip` command:

We recommend installing the specific version of PyTorch and accelerate toolbox [xFormers](https://pypi.org/project/xformers/). You can install these recommended version by pip:
```shell
pip install -r requirements/recommended.txt
pip install scepter
```

## 🧩 Generative Framework

### Tutorials

| Documentation                                      | Key Features                      |
|:---------------------------------------------------|:----------------------------------|
| [Train](docs/en/tutorials/train.md)                | DDP / FSDP / FairScale / Xformers |
| [Inference](docs/en/tutorials/inference.md)        | Dynamic load/unload               |
| [Dataset Management](docs/en/tutorials/dataset.md) | Local / Http / OSS / Modelscope   |


## 📝 Popular Approaches

### Currently supported approaches

|            Tasks             |                   Methods                    | Links                                                                                                                                                                                                                                                       |
|:----------------------------:|:--------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   Text-to-image generation   |                   SD v1.5                    | [![Hugging Face Repo](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Repo-blue)](https://huggingface.co/runwayml/stable-diffusion-v1-5)                                                                                                         |
|   Text-to-image generation   |                   SD v2.1                    | [![Hugging Face Repo](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Repo-blue)](https://huggingface.co/runwayml/stable-diffusion-v1-5)                                                                                                         |
|   Text-to-image generation   |                    SD-XL                     | [![Hugging Face Repo](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Repo-blue)](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0)                                                                                               |
|       Efficient Tuning       |                     LoRA                     | [![Arxiv   link](https://img.shields.io/static/v1?label=arXiv&message=LoRA&color=red&logo=arxiv)](https://arxiv.org/abs/2106.09685)                                                                                                                         |
|       Efficient Tuning       |            Res-Tuning(NeurIPS23)             | [![Arxiv   link](https://img.shields.io/static/v1?label=arXiv&message=Res-Tuing&color=red&logo=arxiv)](https://arxiv.org/abs/2310.19859) [![Page link](https://img.shields.io/badge/Page-ResTuning-Gree)](https://res-tuning.github.io/)                    |
| Controllable image synthesis | [🌟SCEdit(CVPR24)](docs/en/tasks/scedit.md)  | [![Arxiv   link](https://img.shields.io/static/v1?label=arXiv&message=SCEdit&color=red&logo=arxiv)](https://arxiv.org/abs/2312.11392)   [![Page link](https://img.shields.io/badge/Page-SCEdit-Gree)](https://scedit.github.io/)                            |
|        Image editing         |     [🌟LAR-Gen](docs/en/tasks/largen.md)     | [![Arxiv   link](https://img.shields.io/static/v1?label=arXiv&message=LARGen&color=red&logo=arxiv)](https://arxiv.org/abs/2403.19534)   [![Page link](https://img.shields.io/badge/Page-LARGen-Gree)](https://ali-vilab.github.io/largen-page/)             |
|        Image editing         |  [🌟StyleBooth](docs/en/tasks/stylebooth.md) | [![Arxiv   link](https://img.shields.io/static/v1?label=arXiv&message=StyleBooth&color=red&logo=arxiv)](https://arxiv.org/abs/2404.12154)   [![Page link](https://img.shields.io/badge/Page-StyleBooth-Gree)](https://ali-vilab.github.io/stylebooth-page/) |


## 🖥️ SCEPTER Studio

### Launch

To fully experience **SCEPTER Studio**, you can launch the following command line:

```shell
pip install scepter
python -m scepter.tools.webui
```
or run after clone repo code
```shell
git clone https://github.com/modelscope/scepter.git
PYTHONPATH=. python scepter/tools/webui.py --cfg scepter/methods/studio/scepter_ui.yaml
```

The startup of **SCEPTER Studio** eliminates the need for manual downloading and organizing of models; it will automatically load the corresponding models and store them in a local directory.
Depending on the network and hardware situation, the initial startup usually requires 15-60 minutes, primarily involving the download and processing of SDv1.5, SDv2.1, and SDXL models.
Therefore, subsequent startups will become much faster (about one minute) as downloading is no longer required.

### Usage Demo

|              [Image Editing](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Fimage_editing_20240419.webm)              |                [Training](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Ftraining_20240419.webm)                 |              [Model Sharing](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Fmodel_sharing_20240419.webm)               |             [Model Inference](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Fmodel_inference_20240419.webm)              |             [Data Management](https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Fdata_management_20240419.webm)              |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------------------------:|
| <video src="https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Fimage_editing_20240419.webm" width="240" controls></video> | <video src="https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Ftraining_20240419.webm" width="240" controls></video> | <video src="https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Fmodel_sharing_20240419.webm" width="240" controls></video>  | <video src="https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Fmodel_inference_20240419.webm" width="240" controls></video>  | <video src="https://www.modelscope.cn/api/v1/models/iic/scepter/repo?Revision=master&FilePath=assets%2Fscepter_studio%2Fdata_management_20240419.webm" width="240" controls></video>  |

### Modelscope Studio & Huggingface Space

We deploy a work studio on Modelscope that includes only the inference tab, please refer to [ms_scepter_studio](https://www.modelscope.cn/studios/iic/scepter_studio/summary) and [hf_scepter_studio](https://huggingface.co/spaces/modelscope/scepter_studio)


## 🔍 Learn More

- [Alibaba TongYi Vision Intelligence Lab](https://github.com/ali-vilab)

  Discover more about open-source projects on image generation, video generation, and editing tasks.

- [ModelScope library](https://github.com/modelscope/modelscope/)

  ModelScope Library is the model library of ModelScope project, which contains a large number of popular models.

- [SWIFT library](https://github.com/modelscope/swift/)

  SWIFT (Scalable lightWeight Infrastructure for Fine-Tuning) is an extensible framwork designed to faciliate lightweight model fine-tuning and inference.


## BibTeX
If our work is useful for your research, please consider citing:
```bibtex
@misc{scepter,
    title = {SCEPTER, https://github.com/modelscope/scepter},
    author = {SCEPTER},
    year = {2023}
}
```


## License

This project is licensed under the [Apache License (Version 2.0)](https://github.com/modelscope/modelscope/blob/master/LICENSE).


## Acknowledgement
Thanks to [Stability-AI](https://github.com/Stability-AI), [SWIFT library](https://github.com/modelscope/swift/) and [Fooocus](https://github.com/lllyasviel/Fooocus) for their awesome work.
