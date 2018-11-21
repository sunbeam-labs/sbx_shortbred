# sbx_shortbred


[Sunbeam] extension for running [ShortBRED](http://huttenhower.sph.harvard.edu/shortbred).


## Installation

1. Clone into your Sunbeam extensions directory and update your config file

    ```bash
    git clone https://github.com/sunbeam-labs/sbx_shortbred extensions/sbx_shortbred
    cat sunbeam/extensions/sbx_shortbred/config.yml >> sunbeam_config.yml

    ```

2. Get a copy of [USEARCH](https://www.drive5.com/usearch/download.html) and install it in your `sbx_shortbred` folder. Create a symlink to *$CONDA_PREFIX/bin*
    
    ```bash
    PWD=`pwd`
    ln -sf $PWD/usearch10.0.240_i86linux32 $CONDA_PREFIX/bin/usearch
    ```

3. Download the AR-specific marker genes for CARD from the ShortBREAD website OR use the marker genes for a newer version of CARD.

    ```bash
    wget https://bitbucket.org/biobakery/shortbred/downloads/ShortBRED_CARD_2017_markers.faa.gz
    gunzip ShortBRED_CARD_2017_markers.faa.gz
    ```
    
4. Link the marker database to the Sunbeam environment
    ```bash
    mkdir -p $CONDA_PREFIX/opt/shortbred_databases
    ln -sf $PWD/SHORTBRED_CARD_20180628_markers.faa $CONDA_PREFIX/opt/shortbred_databases
    ```
    
5. Update the Sunbeam environment.
    ```bash
    conda env update --name=sunbeam --quiet --file extensions/sbx_shortbred/requirements.txt
    ```

## Running

This extension uses an [isolated Conda environment] for the ShortBRED
installation, so you need to include the `--use-conda` argument when running
Sunbeam:

    sunbeam run --configfile=sunbeam_config.yml --use-conda all_card

[Sunbeam]: https://github.com/sunbeam-labs/sunbeam
[ShortBRED]: http://huttenhower.sph.harvard.edu/shortbred
[isolated Conda environment]: http://snakemake.readthedocs.io/en/stable/snakefiles/deployment.html#integrated-package-management


