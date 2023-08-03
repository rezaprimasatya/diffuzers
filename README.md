
## Installation

To install bleeding edge version of diffuzers, clone the repo and install it using pip.

```bash
git clone https://github.com/rezaprimasatya/diffuzers
cd diffuzers
pip install -e .
```

Installation using pip:
    
```bash 
pip install diffuzers
```

## Usage

### Web App
To run the web app, run the following command:

```bash
diffuzers app
```

### API

To run the api, run the following command:


```bash
diffuzers api
```

Starting the API requires the following environment variables:

```
export X2IMG_MODEL=stabilityai/stable-diffusion-2-1
export DEVICE=cuda
```

If you want to use inpainting:

```
export INPAINTING_MODEL=stabilityai/stable-diffusion-2-inpainting
```

To use long prompt weighting, use:

```
export PIPELINE=lpw_stable_diffusion
```

If you have `OUTPUT_PATH` in environment variables, all generations will be saved in `OUTPUT_PATH`. You can also use other (or private) huggingface models. To use private models, you must login using `huggingface-cli login`.

API docs are available at `host:port/docs`. For example, with default settings, you can access docs at: `127.0.0.1:10000/docs`.


## All CLI Options for running the app:

```bash
❯ diffuzers app --help
usage: diffuzers <command> [<args>] app [-h] [--output OUTPUT] [--share] [--port PORT] [--host HOST]
                                        [--device DEVICE] [--ngrok_key NGROK_KEY]

✨ Run diffuzers app

optional arguments:
  -h, --help            show this help message and exit
  --output OUTPUT       Output path is optional, but if provided, all generations will automatically be saved to this
                        path.
  --share               Share the app
  --port PORT           Port to run the app on
  --host HOST           Host to run the app on
  --device DEVICE       Device to use, e.g. cpu, cuda, cuda:0, mps (for m1 mac) etc.
  --ngrok_key NGROK_KEY
                        Ngrok key to use for sharing the app. Only required if you want to share the app
```

## All CLI Options for running the api:

```bash
❯ diffuzers api --help
usage: diffuzers <command> [<args>] api [-h] [--output OUTPUT] [--port PORT] [--host HOST] [--device DEVICE]
                                        [--workers WORKERS]

✨ Run diffuzers api

optional arguments:
  -h, --help         show this help message and exit
  --output OUTPUT    Output path is optional, but if provided, all generations will automatically be saved to this
                     path.
  --port PORT        Port to run the app on
  --host HOST        Host to run the app on
  --device DEVICE    Device to use, e.g. cpu, cuda, cuda:0, mps (for m1 mac) etc.
  --workers WORKERS  Number of workers to use
```

## Using private models from huggingface hub

If you want to use private models from huggingface hub, then you need to login using `huggingface-cli login` command.

Note: You can also save your generations directly to huggingface hub if your output path points to a huggingface hub dataset repo and you have access to push to that repository. Thus, you will end up saving a lot of disk space. 
