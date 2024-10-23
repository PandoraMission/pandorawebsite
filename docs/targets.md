# Pandora Targets

## Target List
The current list of science targets is given below (as of September 4, 2024). The Pandora target list will be updated as the mission launch date approaches.

{{ read_csv('docs/assets/targets_first20_02162024.csv') }}

## Mass-Radius Plot for Pandora Targets

![](assets/M-R_targets2024.png){: .center}

## Secondary Science Targets
A set of 20 secondary targets have also been identified as potential science targets in the case that some of the targets from the primary target list (above) are removed due to observational and mission requirement considerations. This list of secondary targets is given below.

{{ read_csv('docs/assets/targets_second20_02162024.csv') }}

## Target Selection Methodology
The Pandora Science Team developed a set of criteria and metrics for selecting the best set of exoplanetary targets to not only meet the mission’s requirements but to maximize the science output of Pandora’s prime mission. These metrics incorporate current knowledge about the observatory’s capabilities as well as the science questions that the mission seeks to answer.

The planetary systems composite tables on the [NASA Exoplanet Archive](https://exoplanetarchive.ipac.caltech.edu/) serve as the base of the target list, from which all targets and their information are gathered. This list is then limited to transiting planets only as well as planets with orbital periods < 18 days around host stars with effective temperatures of < 5300 Kelvin. The restriction in planet orbital period ensures that a sufficient number of transits are observable over Pandora’s year-long mission lifetime for each planet target. An upper limit of 5300 K ensures that the target list captures the full range of M- and K-dwarf stars. The magnitude of the host stars is also limited to 7.0 < J < 11.5 and H < 11.0 in order to prevent targets from saturating Pandora’s detectors.

In order to help prioritize which exoplanets Pandora should observe, the Transmission Spectroscopy Metric (TSM, [Kempton, et al. 2018](https://ui.adsabs.harvard.edu/abs/2018PASP..130k4401K/abstract)) is computed for each planet meeting the above criteria. This metric provides an indicator of how strong of a spectral signal a planet’s atmosphere would provide relative to that of other planets. The TSM follows the equation:

$$
TSM = (Scale factor) \times \frac{R^{3}_{p}T_{eq}}{M_{p}R^{2}_{*}} \times 10^{-m_{J}/5}
$$

where $R_{p}$ is the radius of the planet in units of Earth radii, $M_{p}$ is the mass of the planet in units of Earth masses, $R_{*}$ is the radius of the host star in units of Solar radii, $m_{J}$ is the apparent magnitude of the host star in J band, the scale factor is a normalization constant to scale the metric to JWST simulations performed by [Louie, et al. 2018](https://ui.adsabs.harvard.edu/abs/2018AAS...23112806L/abstract), and $T_{eq}$ is the planet’s equilibrium temperature in Kelvin calculated for zero albedo and full day-night heat redistribution according to

$$
T_{eq} = T_{*}\sqrt{\frac{R_{*}}{a}}\left( \frac{1}{4} \right)^{1/4}
$$

where $T_{*}$ is the host star effective temperature in Kelvin and $a$ is the orbital semi-major axis given in the same units as $R_{*}$.

The TSM provides a good indicator of how observable a planet’s atmospheric features will be, but Pandora aims to measure the stellar activity of a diverse range of host stars. Therefore, the Pandora Science Team developed a separate Signal Detection Metric (SDM) to incorporate stellar rotation period into the target list prioritization. The SDM is defined as

$$
SDM = TSM \times (1+wA)
$$

where TSM is the transmission spectroscopy metric as stated above, $A$ is the peak-to-peak amplitude of variability, and $w$ is a weighting factor such that a $w$ of 100 effectively doubles the metric for a star with $A$=1%.

All exoplanets that meet the observational restrictions are ranked by SDM to produce the target lists shown here. The planets with the top 20 SDM values make up the primary targets list and those with the 21st-40th best SDM values make up the secondary target list.
