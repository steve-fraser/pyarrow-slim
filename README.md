# pyarrow-slim

This Docker file and wheel are build upon the pyarrow and arrow version 0.17.0: https://github.com/apache/arrow/

These wheels were build on:
     Alpine = python:3.7-alpine
     Amazon Linux = lambci/lambda:build-python3.7

Paramters passed on arrow ccp build
REFER TO: https://github.com/apache/arrow/blob/master/docs/source/developers/cpp/building.rst

    -DCMAKE_INSTALL_LIBDIR=lib \
    -DCMAKE_INSTALL_PREFIX=$ARROW_HOME \
    -DARROW_PARQUET=on \
    -DARROW_PYTHON=on \
    -DARROW_PLASMA=on \
    -DARROW_WITH_SNAPPY=on \
    -DARROW_BUILD_TESTS=OFF 

Environemnt variable set for pyarrow build:

    export PYARROW_WITH_PARQUET=1
    python setup.py build_ext --build-type=release --bundle-arrow-cpp bdist_wheel
