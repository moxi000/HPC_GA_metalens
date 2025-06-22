# Scalable Performance-Driven Global Optimization of Large-Scale Achromatic Metalenses at Short Visible Wavelengths

This repository contains the computational implementation and experimental data supporting the research paper "Scalable Performance-Driven Global Optimization of Large-Scale Achromatic Metalenses at Short Visible Wavelengths."

## Overview
 
⚠️ Please note: All files will be uploaded after publication.

This project implements a high-performance genetic algorithm optimization framework for designing large-scale achromatic metalenses operating in the short visible wavelength range (400-500 nm). The work focuses on achieving scalable computational performance while maintaining optical design quality for metalenses with varying numerical apertures and element counts.

## Key Features

- **Genetic Algorithm Optimization**: Advanced GA implementation using PyMOO framework
- **Multi-wavelength Design**: Achromatic optimization across 400-500 nm wavelength range
- **Scalable Architecture**: Support for large-scale metalenses (N=223 to N=445 elements)
- **Parallel Processing**: Multi-core and HPC-optimized computation
- **Performance Caching**: Intelligent caching system for computational efficiency
- **Comprehensive Analysis**: Full optical field analysis and visualization

## Repository Structure

```
HPC_GA_metalens/
├── opt-enhanced.py              # Main optimization framework
├── single_wavelength_design.py  # Single wavelength metalens design
├── field_analysis.py            # Optical field analysis tools
├── cache_manager.py             # Computational caching system
├── visualization_utils.py       # Data visualization utilities
├── visualization_config.json    # Visualization configuration
├── ex_db_interpolated.npz      # Precomputed optical database
├── scanatomblue_BAs.fsp        # Lumerical FDTD simulation file
├── results_*/                   # Optimization results directories
├── single_wavelength_*/         # Single wavelength analysis results
└── single_wavelength_cache/     # Cached computation results
```

## Experimental Configurations

The repository includes results for multiple metalens configurations:

### Metalens Sizes
- **N=223**: 223×223 element metalens array
- **N=445**: 445×445 element metalens array

### Numerical Apertures (NA)
- **NA=0.30**: Low numerical aperture configuration
- **NA=0.50**: Medium numerical aperture configuration  
- **NA=0.70**: High numerical aperture configuration

### Wavelength Range
- **Operating Range**: 400-500 nm (short visible spectrum)
- **Design Wavelength**: 450 nm (center wavelength)
- **Spectral Coverage**: 11 discrete wavelengths (400-500 nm, 10 nm steps)

## Results Data

Each optimization result directory contains:

- `settings.json`: Optimization parameters and configuration
- `generations/`: Generation-by-generation optimization data
- `stats/`: Performance statistics and convergence plots
- `errors/`: Error logs and debugging information

Single wavelength analysis directories include:

- Optical field distributions at each wavelength
- Phase and amplitude maps
- FWHM analysis plots
- Structure geometry data (Excel format)
- Wavelength sweep analysis

## Requirements

### Software Dependencies
```
python >= 3.8
numpy
matplotlib
scipy
pandas
pymoo
numba (optional, for acceleration)
joblib (for parallel processing)
psutil
```

### Hardware Requirements
- Multi-core CPU recommended (optimization utilizes parallel processing)
- Minimum 16 GB RAM for large-scale designs
- SSD storage recommended for cache performance

## Usage

### Basic Optimization
```python
python opt-enhanced.py
```

### Single Wavelength Design
```python
from single_wavelength_design import design_single_wavelength_metalens

result = design_single_wavelength_metalens(
    N=223,
    wavelength_nm=450,
    focal_length_um=250,
    pixel_size_um=0.225
)
```

### Field Analysis
```python
import field_analysis as fa

# Analyze optical field performance
fa.analyze_wavelength_performance(wavelength_data, wavelength_nm=450)
```

## Performance Optimization Features

1. **Intelligent Caching**: Results are automatically cached to avoid redundant computations
2. **Parallel Processing**: Multi-core optimization using process/thread pools
3. **Memory Management**: Optimized memory usage for large-scale problems
4. **HPC Compatibility**: Designed for high-performance computing environments

## Data Format

- **Structure Data**: `.npz` format containing geometry and optical parameters
- **Performance Data**: `.csv` files with convergence statistics
- **Visualization Data**: `.png` plots and analysis figures
- **Metadata**: `.json` configuration and parameter files

## Citation

If you use this code or data in your research, please cite:

```
[Paper citation to be added upon publication]
```

## License

This research code is provided for academic and research purposes. Please contact the authors for commercial use permissions.

## Contact

For questions regarding the implementation or data, please open an issue in this repository.

## Acknowledgments

This research was conducted using high-performance computing resources and optical simulation tools. The genetic algorithm optimization framework is built upon the PyMOO optimization library.

---

**Note**: This repository contains computational research data supporting peer-reviewed academic research. All simulations and optimizations were performed using validated optical models and established computational methods.
