# Multi-b-value longitudinal test-retest diffusion MRI brain dataset

Laboratorio de Procesado de Imagen (LPI), ETSI Telecomunicación, Universidad de Valladolid, Valladolid, Spain


## Description:

The dataset was acquired using a Philips Achieva dStream 3T scanner equipped with a 32-channel head coil. The gradient system has a maximum gradient strength of 62 mT/m and a maximum slew rate of 100 mT/m/ms. For each volunteer, the acquisition was divided into four sessions: two sessions performed on consecutive days (test data) and two repeated sessions performed one week later also on consecutive days (retest data). For one volunteer (sub-01), the test data were acquired during two sessions on the same day, whereas the retest data were acquired during two sessions on the same day one week later.

The dataset is available in two variants:
- raw data – **8.3 GB**,
- fully preprocessed and merged data (folder: /derivatives/preproc/) – **39.5 GB**.

All images are provided in the compressed NIfTI format.

We also provide the DTI parameters estimated using FSL v6 and the streamlines corresponding to the white matter bundles:
- DTI parameters (folder: /derivatives/measures/) – **178 MB**,
- streamlines (folder: /derivatives/tractography/) – **409 MB**.


## Participants (n = 11):

Eleven healthy volunteers (5F/6M, aged: 24–48/23–45) have not reported any neurological or neuropsychiatric disorders, nor any head trauma in the past. Exclusion criteria: head trauma, volunteers not compatible with our scanning procedure (e.g., individuals with implants, pacemakers, intrauterine devices), and pregnant volunteers.

## Data acquisition:

- **T1-weighted MRI data:** Anatomical data were acquired using the 3D Turbo Field Echo (TFE) gradient-echo sequence. Reconstruction parameters were: voxel size: 0.9375 × 0.9375 × 1 mm^3, reconstruction matrix: 256 × 256 with 177 sagittal slices covering the brain. 

- **Diffusion-weighted MRI data:** Images were acquired using the single-shot echo-planar imaging (EPI) sequence in anterior-posterior (AP) encoding direction. Acquisition parameters were: TE: 95 ms, EPI factor: 47, effective echo spacing: 0.56 ms, acquisition voxel size: 2.5 × 2.5 × 2.5 mm^3. Reconstruction parameters were: 128 × 128 matrix and 55 axial slices, in-plane resolution of 1.875 × 1.875 mm^2 and slice thickness 2.5 mm. In total, twenty-two b-values were used in the acquisition procedure spread over two sessions:
  - ses-01 and ses-03: b = 10, 20, 30, 50, 80, 100 s/mm^2 (6 diffusion gradient directions for each shell), 200, 300, 400, 500, 600, 700, 800, 900 s/mm^2 (32 diffusion gradient directions per shell), and six non-diffusion-weighted volumes, i.e., volumes acquired at b = 0 s/mm^2,
  - ses-02 and ses-04: b = 1000, 1200, 1400, 1600, 1800, 2200, 2600, 3000 s/mm^2 (32 diffusion gradient directions per shell), and five non-diffusion-weighted volumes.

One additional non-diffusion-weighted volume per session was acquired in the posterior-anterior (PA).


## Data anonymisation:
All files were anonymised at two levels:
  - removal of meta-information from the headers of the NIfTI and JSON files (diffusion-weighted MRI and T1-weighted MRI data),
  - face masking in T1-weighted MRI data.

## Data preprocessing and registration:
- **Preprocessing:** Each of the four sessions was preprocessed separately using the following pipeline: 1) noise estimation and denoising, 2) Gibbs artefacts removal, 3) susceptibility-induced distortions estimation, 4) head movements and eddy current correction, 5) B1 field intensity variations correction, 6) time-varying drift correction.
- **Data registration and concatenation:** Volumes from sessions ses-01 and ses-02, as well as ses-03 and ses-04, were registered and concatenated to generate the test and retest datasets. These data are considered preprocessed.

## Important note:

- The spatial dimensions of the original diffusion-weighted MRI data are **128 × 128 × 55**.
- For preprocessing purposes, the diffusion-weighted MRI data were extended to **128 × 128 × 56** by adding an empty axial slice.


## Reference for the dataset description:

Pieciak T., Guadilla I., Ciupek D., Navarro-González R., Merino-Caviedes S., Villacorta‐Aylagas P., Magdaleno Humayor L., Villa Aparicio M., Rueda-Ramos J., Moro Boyero R., Tristán Vega A., A multi-b-value longitudinal test-retest diffusion MRI brain dataset for model validation and reproducibility assessment, 2026.


## Funding:

This work was funded by the Agencia Estatal de Investigación (Ministerio de Ciencia, Innovación y Universidades of Spain) with the research grant PID2024-158963NB-I00.

## Contact:

- Tomasz Pieciak
- tpieciak@tel.uva.es

