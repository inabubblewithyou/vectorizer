# Image Vectorizer: Intelligent Grouping & Semantic SVG Annotation

This project provides an advanced image vectorization pipeline using state-of-the-art AI for semantic segmentation and grouping, producing annotated SVGs from raster images. The workflow is implemented in the `vectorizer.ipynb` Jupyter notebook, designed for use in Google Colab or any Jupyter environment with GPU support.

## What Does This Script Do?

- **Loads a raster image** (PNG or JPG) from your workspace or via upload.
- **Runs Meta's Segment Anything Model (SAM)** to generate fine-grained segmentation masks for all objects in the image.
- **Merges overlapping masks** to form coherent object segments.
- **Uses KMeans clustering** to group similar segments into logical object groups.
- **Refines masks** for SVG precision using morphological operations.
- **Exports the result as an annotated SVG** with each group and segment as a separate, color-coded path, ready for further animation or interactivity.

## Types of AI Used

- **Segment Anything Model (SAM)**: A foundation model for image segmentation developed by Meta AI. It can segment any object in an image without prior training on specific classes.
- **KMeans Clustering (scikit-learn)**: A classic unsupervised machine learning algorithm used here to group segmented objects based on their spatial centroids, enabling logical grouping of related segments.

## How to Use

1. **Open `vectorizer.ipynb` in Google Colab** (recommended) or your local Jupyter environment.
2. **Run all cells**:
    - The notebook will install required dependencies automatically.
    - It will check for the SAM model checkpoint and download it if missing.
    - You will be prompted to select an existing image or upload a new one (PNG/JPG).
3. **View the segmentation process**:
    - The original image is displayed.
    - The script generates and merges segmentation masks.
    - Masks are grouped and refined.
4. **SVG Export**:
    - The final SVG is saved as `segmentation_output.svg` in your workspace.
    - The SVG is also displayed inline for preview.

## Requirements

- Python 3.7+
- Google Colab or Jupyter Notebook (with GPU recommended)
- Dependencies (installed automatically in the notebook):
    - `segment-anything` (Meta's SAM)
    - `opencv-python-headless`
    - `scikit-learn`
    - `Pillow`
    - `matplotlib`
    - `torch`

## Output

- **`segmentation_output.svg`**: An SVG file with each detected object group as a separate layer, each segment color-coded and ready for further editing, animation, or web use.

## Notes

- The script is interactive and will prompt you for image selection/upload.
- For best results, use high-contrast images with clear object boundaries.
- The SVG output can be further edited in vector graphics editors or used directly in web projects.

---

**AI Models Used:**
- [Segment Anything Model (SAM) by Meta AI](https://github.com/facebookresearch/segment-anything)
- [KMeans Clustering (scikit-learn)](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) 
