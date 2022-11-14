<p align="center">
    <img src="kabuki-text.png" width="500px"/>
</p>
Kabuki is intended to be a Python library for conducting research in offline reinforcement learning, akin to an offline version of Gymnasium or an offline RL version of HuggingFace's datasets library. The goal is to release a fully working beta in late November or early December.

We have a public discord server (which we also use to coordinate development work) that you can join here: https://discord.gg/jfERDCSw if you're interested in it.


## Installation
`pip install numpy cython`

`pip install git+https://github.com/Farama-Foundation/Kabuki.git`

## Downloading datasets

```python
import kabuki

dataset = kabuki.download_dataset("LunarLander-v2-test_dataset")
```

## Uploading datasets

```python
dataset.save(
    ".datasets/LunarLander-v2-test_dataset.hdf5"
)  # todo: abstract away parent directory and hdf5 extension
dataset = kabuki.upload_dataset("LunarLander-v2-test_dataset")
```


## Saving to dataset format
It is not the aim of Kabuki to insist that you use a certain buffer implementation. However, in order to maintain standardisation across the library, we have a standardised format, the `KabukiDataset` class, for saving replay buffers to file. 

This converter will have tests to ensure formatting standards

## Checking available remote datasets

```python
import kabuki

kabuki.list_remote_datasets()
```

## Checking available local datasets
```python
import kabuki
kabuki.list_local_datasets()  # todo: implement
```
Datasets are stored in the `.datasets` directory in your project directory.


