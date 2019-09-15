# Installation

See http://caffe.berkeleyvision.org/installation.html for the latest
installation instructions.

Check the users group in case you need help:
https://groups.google.com/forum/#!forum/caffe-users

## Installing general dependencies

```bash
brew install -vd snappy leveldb gflags glog szip lmdb
brew tap brewsci/science
brew install FORMULA
brew install hdf5 opencv
```

## Finishing with Makes

```bash
# if using Makefile
make clean
make all
make test
make runtest

# else just use cmake
mkdir build
cd build
cmake -DHAVE_PYTHON=ON  -Dpython_version=3 -DPYTHON_EXECUTABLE=/usr/local/bin/python -DCMAKE_CXX_STANDARD=14 -DCMAKE_CXX_COMPILER=clang++  ..

# then install
make all -j8
make pycaffe

# copy to python packages folder
cp -r python/caffe $PYTHONPATH/caffe
cp -r python/matplotlib $PYTHONPATH/matplotlib

# testing
python -c "import caffe;print(caffe.__version__)"
# $ 1.0.0
```
