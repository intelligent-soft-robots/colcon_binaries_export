
.PHONY: all install colcon_build clean

all: colcon_build

colcon_build:
	colcon build --merge-install --cmake-args -DBUILD_TESTING=OFF -DPYBIND11_TEST=OFF

clean:
	rm -rf build install

install:
	./do_install
