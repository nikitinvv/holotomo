# holotomo
Holotomographic reconstruction on GPU


## 1. create conda environment and install dependencies

```console
conda create -n holotomo -c conda-forge cupy swig cmake scikit-build dxchange xraylib matplotlib jupyter astropy olefile
```

Note: CUDA drivers need to be installed before installation

## 2. clone the package and install it

```console
git clone https://github.com/nikitinvv/holotomo

cd holotomo

pip install .
```

## 3. check adjoint tests

```console
cd tests

```

Adjoint test holography. Checking the equity: <G*Gf,f> ?= <Gf,Gf>

```console
python test_holo.py

```

Adjoint test tomography. Checking the equity: <R*Rf,f> ?= <Rf,Rf> 

```console
python test_tomo.py

```

## 4. See jupyter notebook for examples of reconstructions

*data_modeling_phantom.ipynb* - generate holotomography phantom (set of ellipses) data 

*onestep_reconsturction_phantom.ipynb* - reconstruct phantom data with multiPganain, CTF and methods

*data_modeling_chip.ipynb - generate* data for a chip 

*onestep_reconsturction_chip.ipynb* - reconstruct chip data with multiPganain, CTF and methods

*iterative_reconsturction_chip.ipynb* - reconstruct chip data with the Conjugate Gradients method

For modeling parallel the beam geometry one can set magnifications[:] = 1.
Modeling without flat fields can be done by setting prb[:] = 1




### *DTU installation and run jupyter notebook

Connect to a GPU node with X forwarding and load cuda module

```console

voltash -X

module add cuda/12.2

```

then follow instruction above.


