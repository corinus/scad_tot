# scad_tot ![Build & Push Docker Image](https://github.com/SharedControlAutonomousDriving/scad_tot/workflows/Build%20&%20Push%20Docker%20Image/badge.svg)

CMU group's repository for "TakeOverTime" neural network &amp; verification. Affiliated with the [Safe-SCAD](https://www.york.ac.uk/assuring-autonomy/projects/safe-scad/) project.

## Project Structure

* **Network:** The neural network related code can be found in the [network folder](./network).
* **Verification:** The network verification code can be found in the [verification folder](./verification).

## Installation

*Option 1* is to install the project natively, which is recommended for most developers. *Option 2* is to use the docker image, which is mostly intended for running the project in the cloud, however could potentially be used for local development. Installing locally is probably the most comfortable development experience for most developers that aren't familiar with Docker because containers are intended to be ephemeral. Choose whichever option you prefer.

### Option 1: Native Install

This option installs the project natively on your system. Using a `venv` is recommended, but not required. Detailed instructions for this option can be found here: [Native Installation Instructions](./docs/NATIVE_INSTALL.md).

### Option 2: Docker Image

This option runs the project from within a docker container. It is really intended for running the project in the cloud, however you could also use it for local development if you like working in docker containers. Instructions for this method can be found here: [Docker Installation Instructions](./docs/DOCKER_INSTALL.md).

## Download Dataset

There are a few different versions of the dataset, depending on your needs. The current DNNs we have were built using All_Features_ReactionTime.csv.

### Primary Dataset Files

* [Raw Data](https://drive.google.com/drive/folders/1TLz-cKsXMNdIr8A6Aix16QjpRZP_S0BM?usp=sharing) - Raw data from individual simulator runs (separete text file per run)
* [Cleaned Data](https://drive.google.com/drive/folders/1MsyvGP6BblBIB-88ajTFldBWlUFid8RF?usp=sharing) - Cleaned data from individual simulator runs (separate csv file per run)
* [AllData.csv](https://drive.google.com/file/d/1k7fG80Hsb2ZjkbZl_Kx47rE0LiSmaMPG/view?usp=sharing) - Cleaned data combined into a single file (7GB)
* [cleaned_AllData.csv](https://drive.google.com/file/d/1QuZlTzdaqi5BmtiC4wQZTb_6mFv296Lb/view?usp=sharing) - Cleaned up version of AllData.csv (3GB)
* [All_Features_ReactionTime.csv](https://drive.google.com/file/d/1vNT9PopDTy7nUsedAHdg1-VFAKrk6PIO/view?usp=sharing) - cleaned_AllData.csv cleaned further with "ReactionTime" and engineered features (2GB)

## Other dataset files

These are the pre-processed that were used to build, train, and verify the latest version of TOT model. The training and testing data were used to train & test the model, and the verification data consists of the training and testing data combined with incorrectly predicted rows filtered out.

* Training data for v3.2.2: [v3.2.2_train.csv](https://drive.google.com/file/d/1tDqUhCdjHGVmrWHqoKeWLXVG9HhCwUsf/view?usp=sharing)
* Testing data for v3.2.2: [v3.2.2_test.csv](https://drive.google.com/file/d/15jWpFcIh7_KZSNEfqWg5Zv9NW3zqKVbC/view?usp=sharing)
* Verification data for v3.2.2: [verification.csv](https://drive.google.com/file/d/1c8hkHajx-ESUFcS35akhsQ3hMpM_uI22/view?usp=sharing)

## Dataset Info

* [Annotations](https://drive.google.com/file/d/1lyDca6TWOFq1vRsExUxOpx6Y5g1Z7Cpo/view?usp=sharing)
* [Feature Bounds](https://docs.google.com/spreadsheets/d/11i0xvm1eQQ8L82C4-_DEJRmOSk7K-5stjU42DuxRiiY/edit?usp=sharing)

## Running Verification

### Robustness

* To run in a jupyter notebook, see `./verification/robustness.ipynb`
* To run from command line, see `./scripts/robustness.sh` and `./scripts/robustness_asym.sh`
  * View CLI options with `./verification/robustness.py --help`

### Sensitivity

* To run in a jupyter notebook, see `./verification/sensitivity.ipynb`
* To run from command line, see `./scripts/sensitivity.sh` and `./scripts/sensitivity_asym.sh`
  * View CLI options with `./verification/sensitivity.py --help`

### Generating & Verifying Regions

* To run in a jupyter notebook, see `./verification/clustering.ipynb`
