# Stellar Motion Visualization

## Overview
This project visualizes the motion of stars from the Hipparcos star catalog over 100,000 years, creating both static visualizations and an animated representation. The visualization transforms astronomical data into an artistic and informative display, showcasing stellar positions, magnitudes, colors, and proper motions. The project applies data processing and visualization techniques, including CSV handling, matplotlib plotting, and SVG output, inspired by concepts from Week 02 of a creative programming course.

## Data Source
The data is sourced from the [Hipparcos Star Catalog](https://www.kaggle.com/datasets/konivat/hipparcos-star-catalog/data) on Kaggle. The dataset (`hipparcos-voidmain.csv`) contains astrometric and photometric data for stars, including right ascension (RAdeg), declination (DEdeg), visual magnitude (Vmag), proper motions (pmRA, pmDE), and B-V color index.

## Features
- **Data Processing**: Loads and cleans the Hipparcos CSV data, computing distances from parallax values.
- **Static Visualizations**: Generates four plots in an SVG file:
  - Scatter plot of star positions (RA vs Dec) colored by B-V index.
  - Histogram of visual magnitudes.
  - Box plot of proper motions (pmRA and pmDE).
  - Scatter plot of distance vs magnitude.
- **Dynamic Visualization**: Creates an animation showing the motion of stars over 100,000 years based on proper motions, saved as an MP4 (if FFmpeg is installed) or GIF.
- **File Management**: Lists all generated files for cleanup, following best practices.

## Requirements
- **Python Libraries**:
  ```bash
  pip install pandas matplotlib numpy
  ```
- **FFmpeg** (optional, for MP4 output):
  - Install FFmpeg and add it to your system PATH (see [FFmpeg installation guide](https://ffmpeg.org/download.html)).
  - Without FFmpeg, the animation will be saved as a GIF.
- **Data File**: `hipparcos-voidmain.csv` must be in the same directory as the script.

## Installation
1. Clone or download this repository.
2. Place the `hipparcos-voidmain.csv` file in the project directory.
3. Install required Python libraries:
   ```bash
   pip install pandas matplotlib numpy
   ```
4. (Optional) Install FFmpeg for MP4 output:
   - Windows: Download from [gyan.dev](https://github.com/GyanD/codexffmpeg/releases), extract, and add the `bin` folder to your system PATH.
   - Verify with `ffmpeg -version` in a terminal.

## Usage
1. Ensure `hipparcos-voidmain.csv` is in the same directory as `star_motion_viz.py`.
2. Run the script:
   ```bash
   python star_motion_viz.py
   ```
3. The script will:
   - Generate static visualizations saved as `hipparcos_static_viz.svg`.
   - Create an animation saved as `stellar_motion.mp4` (or `stellar_motion.gif` if FFmpeg is unavailable).
   - List all generated files.

## Output Files
- `hipparcos_static_viz.svg`: Static visualizations of star data.
- `stellar_motion.mp4` or `stellar_motion.gif`: Animation of stellar motion over 100,000 years.
- Note: Only files successfully created will be listed at the end of the script run.

## Notes
- The script limits the dataset to the brightest 5000 stars for performance.
- The animation covers 100,000 years in 1000-year steps, showing how stars move based on proper motions.
- B-V color index is used to color stars, representing temperature (blue for hotter, red for cooler).
- Ensure FFmpeg is installed for MP4 output; otherwise, a GIF will be generated, which may be larger in size.

## Acknowledgments
- Data provided by the [Hipparcos Star Catalog](https://www.kaggle.com/datasets/konivat/hipparcos-star-catalog/data) on Kaggle.
- Inspired by Week 02 of a creative programming course, focusing on data processing, matplotlib visualization, and SVG output.

## License
This project is licensed under the MIT License.