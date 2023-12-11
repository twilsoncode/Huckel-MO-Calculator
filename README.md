---
# Hückel Molecular Orbital Calculator for Conjugated Hydrocarbon Molecules
The approach used for this project was to take a valid input molecule name and perform calculations based upon its Simplified Molecular-Input Line-Entry System (SMILES) formula. It should be noted that there are variations of the SMILES formula. For example the canonical variant of the SMILES formula of benzene is C1=CC=CC=C1 whereas the SMILES formula originally developed by Daylight Chemical Information Systems represents benzene as c1ccccc1 where lowercase c indicates an aromatic structure. SMILES formulae are strings which are very useful when representing not only the molecule's formula but also its structure and bond type, something that cannot be done from a molecular formula. This provides further use as SMILES formulae can be integrated into the RDKit library which can provide further information on the properties of the molecule. If there is an internet connection to the [PubChem database](https://pubchem.ncbi.nlm.nih.gov/) database, this program will search the database using `pubchempy` for the valid molecule name to return the SMILES formula. The version of the SMILES formula accessed on the [PubChem database](https://pubchem.ncbi.nlm.nih.gov/) is the canonical variant, this program does also work with non-canonical SMILES variants. If there is not a connection to the [PubChem database](https://pubchem.ncbi.nlm.nih.gov/), the user will input the SMILES formula manually instead. `RDKit` is used to determine the neighbouring carbon atoms for each carbon atom in the SMILES formula, this works for any compound containing only carbon or hydrogen even if it is branched and/or has ring structures. This is fed into a `numpy` array to obtain the Hamiltonian matrix and displayed in a stylised `pandas` `DataFrame`. The Hamiltonian matrix is validated, then eigenvalues and eigenvectors are calculated using the `numpy` library. Each molecular orbital and its linear combination of atomic orbitals are displayed using latex strings and the `IPython.display` `Latex` class. This is to enable a more visually pleasing representation of fractions such as $\frac{1}{2}$ instead of 0.5 and multiples of $\sqrt{2}$ instead of a rounded floating point numbers such as 1.414, something which cannot be achieved with floating point numbers or strings. Scaling factors for the molecular orbital energy level diagram are worked out next which depend upon the minimum non-zero difference between the eigenvalue energy levels. This is important to enable the `matplotlib` graph to scale appropriately for any input. `RDKit` calculates the total number of $\pi$ electrons in the SMILES formula. Since the canonical SMILES formula can be used, `RDKit` is necessary as radical electrons are not explicitly shown in this type of formula, for example the canonical SMILES formula of the allyl radical is C=C[CH2]. The energy level diagram is drawn in `matplotlib` using ordered eigenvectors and eigenvalues for the electron arrow x and y coordinates respectively. The labels for the energy levels are applied using the latex format. `RDKit` is used to apply an image of the molecule's structure formula to the diagram. Finally the total $\pi$ electron energies are calculated from the y coordinates of the $\pi$ electron energy levels in terms of $\beta$ and kJ/mol. Each function specifies the input variable type(s). Docstrings have been provided for each function which can be called using the built in `help()` function.

---
### Software and package versions with documentation links
- [Python 3.11.5](https://www.python.org/downloads/release/python-3115/)
- [Fractions 2.2.0](https://docs.python.org/3.11/library/fractions.html)
- [IPython 8.18.1](https://ipython.readthedocs.io/en/stable/)
- [Math 3.8](https://docs.python.org/3.11/library/math.html)
- [Matplotlib 3.8.2](https://matplotlib.org/stable/index.html)
- [Numpy 1.26.2](https://numpy.org/doc/1.26/)
- [Pandas 2.1.3](https://pandas.pydata.org/pandas-docs/stable/getting_started/overview.html)
- [Pubchempy 1.0.4](https://pubchempy.readthedocs.io/en/latest/)
- [RDKit 2023.9.2](https://www.rdkit.org/docs/index.html)

---
### Installation instructions for the packages used that are not included in the standard python library using `pip`
- `pip install ipython==8.18.1`
- `pip install matplotlib==3.8.2`
- `pip install numpy==1.26.2`
- `pip install pandas==2.1.3`
- `pip install pubchempy==1.0.4`
- `pip install rdkit==2023.9.2`

To check that these packages are installed, use the `pip list` command to see all installed packages and their versions available to be viewed with `pip`.

---
