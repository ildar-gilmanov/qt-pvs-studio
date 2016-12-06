# qt-pvs-studio
Contains pvs-studio.pri file to enable 'pvs' target. See also [PVS-Studio](http://www.viva64.com/en/pvs-studio/)

1. Install [PVS-Studio](http://www.viva64.com/en/pvs-studio/). You could buy PVS-Studio or use it in open source or independed projects for free. [How to use PVS-Studio for Free](http://www.viva64.com/en/b/0457/)
2. You could get this project as git submodule:

    ```
    $ git submodule add --name qt-pvs-studio https://github.com/gilmanov-ildar/qt-pvs-studio.git src/qt-pvs-studio
    $ git submodule update --init --recursive
    ```
3. Then you could include `qt-pvs-studio.pri` file into the end of your `.pro` files.
4. If you use `subdirs` template, just add following code to your subdirs `.pro` file:

    ```
    CONFIG(debug, debug|release): {
        pvs-studio.target = pvs
        pvs-studio.CONFIG = recursive
        QMAKE_EXTRA_TARGETS += pvs-studio
    }
    ```
5. Do `qmake` and `make pvs all` to build your project and run PVS-Studio
6. Fix bugs and continue working
