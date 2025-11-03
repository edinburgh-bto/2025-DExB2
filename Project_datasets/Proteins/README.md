# README Proteins Data-Set Glossary  

---

## Table of Contents
1. [File 1: `pdb_entry_summary.zip`](#file-1-pdb_entry_summaryzip)  
   1. [Identification & Citation](#identification--citation)  
   2. [Experimental Details](#experimental-details)  
   3. [Composition Statistics](#composition-statistics)  
   4. [Geometry & Connectivity](#geometry--connectivity)  
   5. [Model-Quality Metrics](#model-quality-metrics)  
   6. [Biological Annotation](#biological-annotation)  
2. [File 2: `pdb_results_enrich_all.csv`](#file-2-pdb_results_enrich_allcsv)  
   1. [Identification & Ion Listing](#identification--ion-listing)  
   2. [Geometric Contact Statistics](#geometric-contact-statistics)  
   3. [Residue-Level Contact Counts](#residue-level-contact-counts)  
   4. [Ion Properties](#ion-properties)  

---

## File 1: `pdb_entry_summary.zip`

### Identification & Citation
**`pdb ID`**  
Four-character identifier (e.g. `1ABC`) uniquely naming a structure entry in the Protein Data Bank (PDB).

**`Release Date`**  
Calendar date on which the PDB entry was first made public.

**`PubMed ID`**  
Identifier of the primary paper in PubMed. *Blank/NaN = no publication yet.*

**`Journal Name (Abbrev)`**  
Abbreviated journal title (e.g. `J. Mol. Biol.`).

---

### Experimental Details
**`Experimental Method`**  
Main technique used to determine the structure (X-ray, cryo-EM, NMR, …).

**`Resolution (Å)`**  
Smallest distinguishable distance in the experimental data; lower = sharper model.

**`Deposited Model Count`**  
Number of full coordinate sets in the entry (important for NMR ensembles).

---

### Composition Statistics
**`Total Polymer Instances (Chains)`**  
Total number of biopolymer chains (protein, DNA, RNA, hybrid).

**`Total Non-polymer Instances`**  
Number of individual small-molecule components (ligands, ions, cofactors, …).

**`Polymer Residues per Deposited Model`**  
Sum of all amino-acid/nucleotide residues in one model.

**`Number of Non-H Atom per Deposited Model`**  
Total non-hydrogen atoms present in a single model.

**`Molecular Weight per Deposited Model`**  
Calculated mass of everything in one model (kDa).

**`Distinct Molecular Entities`**  
Count of chemically unique molecules (identical chains counted once).

**`Entry Polymer Types`**  
How many classes of biopolymer occur (protein, DNA, …).

**`Distinct Non-polymer Entities`**  
Unique small-molecule/ion types.

---

### Geometry & Connectivity
**`Water Molecules per Deposited Model`**  
Ordered waters present.

**`Disulfide Bond Count per Deposited Model`**  
Number of annotated S–S bonds.

**`cis-Peptide Bond Count per Deposited Model`**  
Number of cis peptide bonds.

---

### Model-Quality Metrics
**`R Free`**  
Fit to a reserved test set; typically < 0.25 for good crystallographic models.

**`R Work`**  
Fit to the working refinement data set (slightly lower than *R*<sub>Free</sub>).

---

### Biological Annotation
**`polymer_entity_ids`**  
List of PDB numerical IDs for each unique polymer entity (e.g. `[1, 2]`).

**`Entry Polymer Composition`**  
Text summary such as `Protein(2), DNA(1)`.

**`Distinct DNA / RNA / Protein / NA Hybrid Entities`**  
Counts of unique DNA, RNA, protein, or hybrid chains.

**`Bound Components`**  
Three-letter ligand codes of molecules bound to the macromolecule(s).

**`source_organisms`**  
Organisms from which the biomolecules were obtained or engineered.

**`parent_organisms`**  
Original natural organisms encoding recombinant sequences.

**`uniprot_ids`**  
UniProtKB accession numbers for each protein entity.

**`ec_numbers`**  
Enzyme Commission numbers describing catalytic activity.

**`entity_names`**  
Human-readable names (e.g. *DNA polymerase I*, *ATP*).

---

## File 2: `pdb_results_enrich_all.csv`

### Identification & Ion Listing
**`PDB code`**  
Same four-character PDB identifier as above.

**`Ligand type`**  
Sequential index for each unique ion type within a structure (1 = only one type present).

**`Ligand number`**  
Copy number of the ion of that type.

**`Ion`**  
Chemical identity of the ion (e.g. `MG`, `ZN`).

**`Chains`**  
Chain(s) that the ion contacts: `A` = only chain A; `B_A` = sits at an interface between chains B and A.

---

### Geometric Contact Statistics
| Column | Meaning |
|--------|---------|
| **`Number of hydrogen bonds`** | Direct coordination bonds to the polymer. |
| **`Number of non-bonded contacts`** | Longer, non-bonded contacts. |
| **`Average / Std / Max / Min Distance HB (Å)`** | Statistics for the shorter coordination bonds. |
| **`Average / Std / Max / Min Distance NB (Å)`** | Corresponding statistics for non-bonded contacts. |

---

### Residue-Level Contact Counts
Twenty columns, one per standard amino acid, named `Unique ALA count`, `Unique ARG count`, …  
Each gives the number of distinct residues of that type that interact with the ion (not the number of individual atom contacts).

---

### Ion Properties
**`molecular_weight`**  
Molecular weight of the ion (Da).

**`formal_charge`**  
Formal charge.

**`name`**  
Full name of the ion.

---

*End of glossary.*


