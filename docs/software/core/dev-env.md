# NOVA Core Development Environment

```
INCOMPLETE: STILL A WORK IN PROGRESS
Need clarification from Intel regarding OpenVINO roadmap.
```

This document describes the software stack and the installation steps required to configure a full Ximira development environment. This includes:

  - Base Operating System
  - Core Packages, Frameworks, and Runtimes
  - Other Considerations
  
## Base Operating System

Ximira NOVA devices target Canonical's Ubuntu Desktop Linux distribution. As a policy goal, Ximira will aim to support the latest long-term support (LTS) release within one year of general availability, but not before the first service release. In order to remain current with all security and performance-related updates, we expect to perform regular updates after sufficient regression testing.

As of the writing of this this document, the current LTS release is 22.04 (Jammy Jellyfish). All notes and instructions herein are based on this release and should be updated accordingly as required.

This document assumes a bare-metal installation of Ubuntu Desktop. However, assuming proper hardware passthrough and/or abstraction, it should be possible to leverage a virtual environment, as well.

## Core Packages, Frameworks, and Runtimes

The following packages should be installed onto the base OS.

### Install Common Library Dependencies and Intall GPU OpenCL Drivers

*[Source Instructions](https://github.com/openvinotoolkit/openvino_notebooks/wiki/Ubuntu)*

By default, Ubuntu doesn't install many core development tools.  Add these as follows:

```sh
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install python3-venv build-essential python3-dev git-all
```

NOVA leverages the onboard Intel Iris Xe integrated GPU if it is available. To install the OpenCL drivers required to access the GPU, run the following:

```sh
sudo apt-get install intel-opencl-icd
```

### Install OpenVINO Runtime (version 2022.1)

Follow the [installation instructions](https://www.intel.com/content/www/us/en/developer/tools/openvino-toolkit/download.html) to install version 2022.1 of the Intel OpenVINO Runtime using APT.

In summary:

```sh
wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

sudo apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

echo "deb https://apt.repos.intel.com/openvino/2022 focal main" | sudo tee /etc/apt/sources.list.d/intel-openvino-2022.list

sudo apt update

sudo apt install openvino-2022.1.0
```

### Install and Activate a Ximira Python Virtual Environment

It is generally best practice to create and leverage Python virtual environments to avoid corruption of or conflicts with your global Python installation(s). This document assumes that you will create and activate one called `ximira-env` located directly below your user home directory.

```sh
python3 -m venv ~/ximira-env
```

You will need to activate the virtual environment each time you wish to leverage the tools installed into this environment. To do so run the following.

```sh
source ~/ximira-env/bin/activate
```

*Note: if you need to deactivate the environment later, you can simply type `deactivate`.*

Finally, insure that you have the latest version of pip installed.

```sh
python -m pip install --upgrade pip
```


### Install and Test OpenVINO Development Tools

Follow the [installation instructions](https://www.intel.com/content/www/us/en/developer/tools/openvino-toolkit/download.html) to install version 2022.1 of the Intel OpenVINO Development Tools using PIP.

Ensure that you have activated the Ximira virtual environment and then install the tools using pip. The pip install command below includes the complete set of CV model framework optimizers (as of OpenVINO 2022.1). This list can be pared down to only those relevant to your development.

```sh
source ~/ximira-env/bin/activate

pip install openvino-dev[caffe,ONNX,kaldi,pytorch,mxnet,tensorflow2]==2022.1.0
```

After completion, test the install using both of the following.

```sh
```

If neither reports an error, your OpenVINO installation is complete.

*[Source Instructions](https://github.com/openvinotoolkit/openvino_notebooks/wiki/Ubuntu)*







Clone the test OpenVINO Jupyter Notebooks:

```
git clone --depth=1 https://github.com/openvinotoolkit/openvino_notebooks.git
```

And install the 


### Compile OpenCV

### Install DepthAI

### Install ROS2



## Other Considerations and Notes

