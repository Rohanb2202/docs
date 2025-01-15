
# Crystal Structure Prediction (CSP) Application Documentation

## Overview
The Crystal Structure Prediction (CSP) application is designed to predict and analyze how molecules transition from the gas phase to solid phase crystal structures. This documentation provides details about the requirements, architecture, and implementation of the CSP workflow.

## Problem Definition 
The application supports researchers in:
- Predicting crystal structures from molecular conformers.
- Visualizing 3D molecular structures.
- Analyzing crystal density distributions.
- Evaluating lattice energies.
- Comparing and ranking crystal structures.

### Primary Users

1. **Bioinformaticians**
   - Professional researchers working with protein and molecular data
   - Need: Systematic analysis of molecular structures and their properties
   - Usage pattern: Batch processing and comparative analysis

2. **Researchers**
   - Chemistry and materials science researchers
   - Need: Detailed investigation of crystal structures for research purposes
   - Usage pattern: In-depth analysis and validation of predictions

## Technical Architecture
The application consists of three primary tabs, each with specific functionality and requirements:

### Tab 1: 3D Conformation Search
- **Input**: SMILES notation.
- **Backend**: Existing code can be reused as-is.
- **Output**: Visualization of all cluster representatives.
- **Features**: 
  - 3D conformer visualization.
  - Cluster analysis.
  - Reference conformer selection (optional).

### Tab 2: Crystal Structure Sampling
- **Input**: Conformers generated in Step 1 (.xyz files).
- **User Options**:
  - Number of candidate crystal structures (Text box).
  - Method selection (Dropdown):
    - PyXtal
    - Crystalmath
    - CDVAE
  - Space group (Text box).
  - Z (number of molecules in the unit cell) (Text box).
- **Output**:
  - Candidate crystal structures (.cif files).
  - Histogram visualization of crystal density distribution.
- **Technical Support**: Backend code available with support from Sourav Mondal (PyXtal).

### Tab 3: Preliminary Screening
- **Input**: 
  - All candidate crystal structures from Step 2 (.cif files).
  - AI/ML model for predictions (provided).
- **Output**:
  - Crystal density vs. lattice energy plot.
  - Rank-ordered table with:
    - CIF file names.
    - Rankings.
    - Predicted lattice energy.
- **Visualization Features**:
  - Interactive plot with clickable points/boxes.
  - Structure overlay capability for comparison.
  - Integration of density vs. lattice energy plot.
- **Recommended Tools**:
  - nglview or ASE for structure visualization.

## Implementation Requirements

### Frontend Development
1. **Responsive Design**: The application must be compatible with various screen sizes and offer an intuitive interface for scientific users.
2. **Visualization Components**: The application will include:
   - 3D molecular structure viewer.
   - Interactive plots and histograms.
   - Data tables with sorting functionality.
3. **User Controls**: Ensure input validation for all text fields, dropdown menus for method selection, and interactive plot elements.

### Backend Integration
1. **API Integration**: Connect the application to existing backend services, handle file uploads/downloads (.xyz, .cif files), and process model predictions.
2. **Data Processing**: Generate crystal structure predictions, calculate crystal densities, and process lattice energy predictions.

## Technical Stack
- **Frontend**: Next.js with TypeScript & Tailwind CSS.
- **Visualization Libraries**: 
  - NGL Viewer or ASE for molecular visualization.
  - Plotly or D3.js for interactive plots.
- **Deployment**: Docker container via bootcamp.aganitha.ai.

## Exit Criteria
The project will be considered complete when:
1. All three tabs are fully functional.
2. Data visualization meets scientific requirements.
3. The UI is responsive and user-friendly.
4. Backend integration is complete and tested.
5. Documentation is comprehensive.

## Project Deliverables
1. **Working Application**: The frontend will be deployed in a Docker container and accessible via bootcamp.aganitha.ai.
2. **Documentation**: 
   - Technical documentation.
   - User guide.
   - API documentation.
3. **Source Code**: 
   - Well-structured, commented code.
   - Reusable components.
   - A testing suite.

## Notes for Developers
- The UI layout shown in the reference images is a suggestion, and developers are encouraged to improve the design.
- Focus on scientific accuracy, usability, and modularity for future extensions.
- Consider performance optimization for handling large datasets.
- Implement error handling for all API calls.
- Follow best practices for scientific software development.
