
to install:

    sudo ./apt_depencencies
    sudo ./pip3_dependencies
    ./configure
    sudo make install

to change the install root directory, for example:

    ./configure --prefix=/path/to/dir

(the default is /usr/local)

to change the python installation folder, for example:

    ./configure --pythondir=/path/to/site-packages/

(the default is the output of : python3 -c 'import site; print(site.getsitepackages()[0])')
