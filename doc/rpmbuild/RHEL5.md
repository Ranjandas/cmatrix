The below steps could be followed for building cmatrix rpm on CentOS 5 or RHEL 5

* Clone the repo to the build machine based on CentOS 5/RHEL 5
  
    ```
    git clone https://github.com/Ranjandas/cmatrix
    ```

* Create gzipped tarball of the directory with name `cmatrix-1.2a`

    ```
    mv cmatrix cmatrix-1.2a && tar -czf cmatrix-1.2a.tar.gz cmatrix-1.2a
    ```

* Install packages required for successfull build

    ```
    yum install gcc ncurses-devel rpm-build make xorg-x11-font-utils
    ```

* Build RPM using rpmbuild

    ```
    rpmbuild --define 'dist .el5' -tb cmatrix-1.2a.tar.gz
    ```

Once the above command finishes the RPM will be available at `/usr/src/redhat/RPMS/x86_64`

* Install the RPM

    ```
    rpm -ivh cmatrix-1.2a-1.el5.x86_64.rpm
    ```

* Launch cmatrix using `cmatrix` command
