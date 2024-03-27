# Data Preprocessing Pipeline for Acquiring 3D Molecular Structures of Glycans

This is the data preprocessing pipeline to acquire 3d molecular structures of molecules (specifically glycans) from a dataset. Our aim was to fine-tune the 3DMolMS model ([3DMolMS Github](https://github.com/JosieHong/3DMolMS)), which can predict the tandem mass spectra of a given molecule, on larger molecules. The model requires the 3d molecular structure of the molecules to generate predictions. Upon finding datasets that contained glycans and their spectra, we had to find the 3d molecular structure of the glycans.

## Steps:

1. **Identifying Glycan Datasets**: The initial step involved sourcing datasets containing glycans and their associated spectra.

2. **Normalization of Glycan Nomenclature**: The glycan datasets adopted a different nomenclature for representing glycan formulae compared to the format required by the 3D molecular structure retrieval tool. To address this, we needed to convert the glycan formulae into the appropriate nomenclature. We achieved this conversion using a molecular formula converter available at [GlycoGlyph](https://glycotoolkit.com/Tools/GlycoGlyph/).

3. **Web Scraping for Molecular Structures**: Utilizing Selenium in Python, we performed web scraping to automate the retrieval of 3D molecular structures. The process involved:
   - Inputting each glycan formula from our datasets into the formula converter.
   - Inputting the converted formulae into the 3D molecular structure finder website specified [here](https://pubs.acs.org/doi/10.1021/acs.jcim.1c00917) to acquire the corresponding 3D molecular structures.

## Dataset Reference:
Datasets used in this preprocessing pipeline can be accessed [here](https://chemdata.nist.gov/dokuwiki/doku.php?id=peptidew:oligo).
