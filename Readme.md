

## Setting up environment variables

Set the proper values for some of the environment variables. 

1. Ideally you want to provide some location for you to download 
   the Quandl data files. These should be in a single folder defined 
   by `ZIPLINE_ROOT` environment  variable. Remember that this will
   end up taking some amount of space, and you want to provide as much
   space as possible.
2. Also you want the Quandl API key to be defined for zipline in the 
   `QUANDL_API_KEY` environment variable. Rememebr that this is _not_
   used by Quandl, but rather by zipline. For anything to do with Quandl
   you want to keep the key in your `~/.quandl` folder. Alternatively
   read the environment variable and set 
   `quandl.ApiConfig.api_key = "your API Key"` before any calculations.


```sh
set -g -x ZIPLINE_ROOT   /path/to/zipline/folder
set -g -x QUANDL_API_KEY <your API Key> 
```

## Generating the virtual environment

Set up the required libraries

```sh
#!/bin/bash

python3 -m venv env
source env/bin/activate.fish

pip3 install --upgrade pip
pip3 install numpy       # required for zipline
pip3 install cython      # required for zipline
pip3 install setuptools  # required for zipline
pip3 install zipline     # 
pip3 install jupyter     # 
pip3 install quandl      # data source
pip3 install pytz        # time zone calculations
```

## Load the virtual environment

This is something that a lot of people forget to do

```sh
source env/bin/activate.fish
```

