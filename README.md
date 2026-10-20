# BRISC 2025 train–test overlap audit

Analysis notebooks for the article:

> Alhawat, M.; Al Hassan, A.; Mouhamadou, M.; Esper, P.; Habib, M.; Hage-Diab, A.; Kanaan, M.; Diab, A. *Toward Reliable Evaluation of Brain Tumor AI: Hidden Train-Test Overlap in the BRISC 2025 MRI Benchmark.* Submitted to *Brain Sciences* (MDPI), 2026.

The study searched every official BRISC 2025 test image for relatives in the training set: plain copies, mirror-image copies, near-duplicates and slices of the same patient. It then measured how much training on these relatives raises classification and segmentation scores, using a randomized crossover design. No MRI image is redistributed here.

## Notebooks

| Notebook | What it does |
|---|---|
| `notebooks/BRISC_contamination_controlled_multitask_v3.ipynb` | Main analysis, rounds 1–3, saved with its outputs. It downloads the public datasets, audits the official split, builds the groups of related images, trains every model (three seeds) and computes the pre-specified analyses and the explanation tests. |
| `notebooks/BRISC_round4_addendum.ipynb` | Round 4, with no training. It recomputes the corrected statistics behind the appendix tables of the article from the per-image predictions that the main notebook saves. |

Run the main notebook first. The round-4 notebook reads the main notebook's saved run folders (`MyDrive/brisc_runs`) from Google Drive.

## Data sources

- BRISC 2025, Kaggle `briscdataset/brisc2025`, version 6 (doi:10.34740/KAGGLE/DS/7632487), CC BY 4.0.
- Figshare brain tumor dataset, Cheng (doi:10.6084/m9.figshare.1512427), CC BY 4.0.

## Environment

Google Colab with one NVIDIA Tesla T4 GPU; Python 3.13.15, PyTorch 2.11.0 (CUDA 13.0), NumPy 2.1.3, pandas 2.2.3, SciPy 1.16.3, scikit-learn 1.6.1, OpenCV 4.14.0.

## Licence

MIT License, see `LICENSE`.

## Contact

Marwan Alhawat (51630914@students.liu.edu.lb) and Ahmad Al Hassan (92110021@students.liu.edu.lb), Lebanese International University.
