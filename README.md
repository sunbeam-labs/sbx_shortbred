# sbx_shortbred


[Sunbeam] extension for running [ShortBRED](http://huttenhower.sph.harvard.edu/shortbred), adapted from
[eclarke](https://github.com/eclarke)'s
[shortbred-snakemake](https://github.com/eclarke/shortbred-snakemake).


## Installation

    git clone https://github.com/zhaoc1/sbx_shortbred
    cat sunbeam/extensions/sbx_metaphlan/config.yml >> sunbeam_config.yml
    
    

## Running

This extension uses an [isolated Conda environment] for the ShortBRED
installation, so you need to include the `--use-conda` argument when running
Sunbeam:

    sunbeam run --configfile=sunbeam_config.yml --use-conda all_shortbred

[Sunbeam]: https://github.com/sunbeam-labs/sunbeam
[ShortBRED]: http://huttenhower.sph.harvard.edu/shortbred
[isolated Conda environment]: http://snakemake.readthedocs.io/en/stable/snakefiles/deployment.html#integrated-package-management


