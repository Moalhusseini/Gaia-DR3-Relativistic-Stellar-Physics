# Reliability of Relativistic Surface-Effect Estimates from Gaia DR3 Stellar Parameters

## Overview

This project investigates the reliability and physical interpretation of stellar surface quantities derived from stellar mass and radius estimates in the Gaia Data Release 3 (DR3) catalogue.

The study combines classical gravitational calculations with selected quantities from the Schwarzschild exterior solution. It compares two stellar populations, Main Sequence and Red Giant Branch (RGB), and examines parameter uncertainty, exploratory correlations, and the consistency between calculated gravitational-redshift estimates and published Gaia FLAME values.

## Objectives

- Calculate selected Newtonian and Schwarzschild-exterior quantities from stellar mass and radius.
- Compare the physical properties of Main Sequence and RGB stars.
- Examine how uncertainty in mass and radius propagates into derived surface gravity.
- Explore relationships between effective temperature and the Kretschmann scalar.
- Assess the sensitivity of selected exploratory results to the criterion `RUWE < 1.4`.
- Investigate differences between calculated gravitational-redshift estimates and Gaia DR3 FLAME values.

## Data

The analysis uses stellar parameters from **Gaia DR3**, including stellar mass, radius, effective temperature, surface gravity, photometric measurements, astrometric quality indicators, and evolutionary-stage information.

The initial matched catalogue contained **545,927 rows**. After selecting the evolutionary stages used in this study, the final sample contained **414,970 stars**:

| Stellar population | Number of stars |
|---|---:|
| Main Sequence | 331,192 |
| Red Giant Branch | 83,778 |
| **Total** | **414,970** |

The selected sample has non-uniform sky coverage and should not be interpreted as a complete or representative sample of the Milky Way.

## Methodology

The workflow consists of the following stages:

1. **Data preparation:** Select relevant Gaia DR3 parameters and identify the stellar populations using the FLAME evolutionary-stage parameter.
2. **Exploratory analysis:** Examine sample characteristics and compare stellar mass, radius, surface gravity, and other derived quantities between the two populations.
3. **Physical calculations:** Derive surface gravity, gravitational potential, escape velocity, Schwarzschild radius, compactness, gravitational redshift, time-dilation factor, and the exterior Kretschmann scalar from stellar mass and radius.
4. **Uncertainty analysis:** Examine the reported mass and radius intervals and calculate conservative bounds for derived surface gravity.
5. **Sensitivity analysis:** Repeat the selected temperature–Kretschmann correlation analysis using the criterion `RUWE < 1.4`.
6. **Gravitational-redshift comparison:** Compare calculated estimates with Gaia DR3 FLAME values while accounting for possible differences in their estimation procedures.

## Main Findings

- The two selected populations show clear differences in their median stellar properties. Main Sequence stars have a median mass of approximately **0.809 solar masses** and a median radius of **0.827 solar radii**. RGB stars have a median mass of approximately **1.553 solar masses** and a median radius of **5.434 solar radii**.
- The median derived surface gravity is approximately **313.94 m/s²** for the Main Sequence sample and **14.54 m/s²** for the RGB sample.
- The median theoretical gravitational-redshift estimates derived from mass and radius are approximately **2.03 × 10⁻⁶** for Main Sequence stars and **6.36 × 10⁻⁷** for RGB stars.
- The Spearman correlation between effective temperature and the logarithm of the Kretschmann scalar is negative for the Main Sequence sample (\(\rho=-0.7575\)) and positive but weaker for the RGB sample (\(\rho=0.2786\)).
- Applying `RUWE < 1.4` produces only small changes in these correlation coefficients. This indicates stability with respect to this particular criterion, but does not rule out other sources of bias.
- The calculated gravitational-redshift estimates and published Gaia FLAME values show discrepancies that require further investigation. The comparison is treated as a diagnostic result rather than proof of an error in the Gaia catalogue.

## Physical Framework

The calculations use standard expressions, including:

$$
g=\frac{GM}{R^2}
$$

$$
R_s=\frac{2GM}{c^2}
$$

$$
z=\left(1-\frac{2GM}{Rc^2}\right)^{-1/2}-1
$$

where \(G\) is the gravitational constant, \(M\) is stellar mass, \(R\) is stellar radius, and \(c\) is the speed of light.

The relativistic expressions are evaluated using the Schwarzschild exterior solution. Their application to real stars is interpreted within the assumptions and limitations of the available catalogue parameters.

## Limitations

- The selected sample has non-uniform spatial coverage.
- Derived physical quantities share mass and radius inputs, so correlations between them are not independent physical tests.
- Conservative gravity bounds do not account for the unavailable joint covariance between mass and radius.
- The gravitational-redshift comparison remains unresolved because the underlying calculation procedures may differ.
- The temperature–Kretschmann analysis is exploratory and does not independently test general relativity.

## Repository Structure

```text
gaia-dr3-stellar-surface-effects/
├── README.md
├── paper/
│   ├── main.tex
│   └── Gaia_DR3_Stellar_Parameters.pdf
├── notebooks/
│   └── analysis.ipynb
└── figures/
    ├── sky_sample_map.jpeg
    ├── mass_radius_relationship.png
    └── gravitational_redshift_comparison.png
```

The filenames above describe the proposed structure. Update them to match the files actually uploaded to the repository.

## Data Source

Gaia Data Release 3 is provided by the European Space Agency (ESA) and the Gaia Data Processing and Analysis Consortium (DPAC).

- [Gaia Archive](https://gea.esac.esa.int/archive/)
- [Gaia DR3 Documentation](https://gea.esac.esa.int/archive/documentation/GDR3/)

## Author

**Mohammad Al-Husseini**  
Department of Business Intelligence and Data Analytics  
University of Petra, Amman, Jordan

## Acknowledgements

The author gratefully acknowledges the European Space Agency and the Gaia Data Processing and Analysis Consortium for making Gaia DR3 and its accompanying documentation publicly available. These resources provided the data and documentation used in this study.

## Research Status

This repository presents a data-driven investigation of stellar surface quantities derived from Gaia DR3. The results should be interpreted within the methodological assumptions and limitations described in the paper.

