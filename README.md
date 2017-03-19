Jekyll Docker Images
====================

This repository contains the source for building static websites using
[Jekyll](https://jekyllrb.com/) that will be served with
[nginx 1.8](http://nginx.org/) for a reproducible Docker image using
[source-to-image](https://github.com/openshift/source-to-image).
The resulting image can be run using [Docker](http://docker.io) or preferably
hosted in OpenShift.

For more information about using these images with OpenShift, please see the
official [OpenShift Documentation](https://docs.openshift.org/latest/using_images/s2i_images/ruby.html).

Versions
---------------
Ruby versions currently provided are:
* ruby-2.2

nginx versions currently provided are:
* nginx-1.8

CentOS versions currently supported are:
* CentOS7

Installation
---------------
To build the Jekyll Builder Ruby image:
*  **CentOS based image**

    This image is available on DockerHub. To download it run:

    ```
    $ docker pull mrjoshuap/s2i-jekyll-nginx-18-centos7
    ```

    To build this image from scratch run:

    ```
    $ git clone https://github.com/mrjoshuap/s2i-jekyll-nginx-18-centos7.git
    $ cd s2i-jekyll-nginx-18-centos7
    $ make
    ```

Usage
---------------------------------
To build a Jekyll application image:

* install S2I from https://github.com/openshift/source-to-image

* perform a source to image build on your Jekyll site source

  ```
  # s2i build git://<source code> jekyll-nginx-18-centos7 <application image>
  ```

3. run the resulting application image

  ```
  # docker run -p 8080:8080 <application image>
  ```
