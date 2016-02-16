Installation instructions
=========================

Windows, binary
---------------

Add the mex and tools subdirectories to your MATLAB path and/or the Python module to your Python path.

Linux, from source
------------------

Requirements: g++, boost, CUDA (driver+toolkit), Matlab and/or Python (2.7 or 3.x)

.. code-block:: bash

  cd build/linux
  ./autogen.sh   # when building a git version
  ./configure --with-cuda=/usr/local/cuda \
              --with-matlab=/usr/local/MATLAB/R2012a \
              --with-python
              --prefix=/usr/local/astra
  make
  make install

Add /usr/local/astra/lib to your LD_LIBRARY_PATH. Add /usr/local/astra/matlab and its subdirectories (tools, mex) to your matlab path. Add /usr/local/astra/python to your PYTHONPATH.

Alternatively, one can also install the library by using the conda command:

.. code-block:: bash

conda install -c astra-toolbox astra-toolbox


NB: Each matlab version only supports a specific range of g++ versions. Despite this, if you have a newer g++ and if you get errors related to missing GLIBCXX_3.4.xx symbols, it is often possible to work around this requirement by deleting the version of libstdc++ supplied by matlab in MATLAB_PATH/bin/glnx86 or MATLAB_PATH/bin/glnxa64 (at your own risk).

Windows, from source using Visual Studio 2008
---------------------------------------------

Requirements: Visual Studio 2008, boost, CUDA (driver+toolkit), matlab. Note that a .zip with all required (and precompiled) boost files is available from our website.

Set the environment variable MATLAB_ROOT to your matlab install location. Open astra_vc08.sln in Visual Studio. Select the appropriate solution configuration. (typically Release_CUDA|win32 or Release_CUDA|x64) Build the solution. Install by copying AstraCuda32.dll or AstraCuda64.dll from bin/ and all .mexw32 or .mexw64 files from bin/Release_CUDA or bin/Debug_CUDA and the entire matlab/tools directory to a directory to be added to your matlab path.
