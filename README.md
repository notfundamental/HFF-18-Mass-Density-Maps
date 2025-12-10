**Hubble Frontier Fields – Radial Curvature Shoulders (Dec 2025)**
A reproducible analysis of κ-map curvature features across all CATS HFF clusters
(this is a clean up and an update the HFF-18-Mass-Density-Maps notebook)

**Overview**

This repository contains a full, reproducible analysis of radial curvature profiles in the Hubble Frontier Fields (HFF) galaxy clusters, using κ (convergence) maps from three independent strong-lensing teams:

CATS (Jauzac et al.)

Sharon et al.

Glafic (Oguri et al.)

Across all clusters and mapmakers, we identify a stable downward-curvature “shoulder” at a characteristic physical scale. The feature is:

Present in every reconstruction team,

Robust to azimuthal anisotropy (jackknife),

Robust to centre uncertainty (jitter),
  
Robust to pixel scale / binning,
  
Not attributable to map edges or smoothing artefacts.

The analysis is purely observational and geometric. No assumptions about dark matter or modified gravity enter the pipeline.

Mapmaker differences (multiple CATS versions),

Azimuthal anisotropy (jackknife wedge tests),

Centre mis-identification (randomised centroid jitter),

Pixel-scale or binning choices,

Map-edge artefacts.


The analysis is purely geometric and observational; it relies on no theoretical assumptions about dark matter or modified gravity.

**Data Sources**

The notebook uses public κ maps from:

CATS (Jauzac et al.)

https://archive.stsci.edu/pub/hlsp/frontier/
https://massmaps.eu

https://sites.google.com/site/massmapshff/home

Sharon et al.

https://archive.stsci.edu/pub/hlsp/frontier/

Available via the Frontier Fields lens modeling repository.

Glafic (Oguri et al.)

https://archive.stsci.edu/pub/hlsp/frontier/

http://www.slac.stanford.edu/~oguri/glafic/

All maps include WCS metadata for consistent angular → physical coordinate conversion.

No proprietary data or pre-processing is required.

**What the Notebook Does**
1. Load & harmonise maps from all three teams

Uniform WCS extraction

Conversion to physical radius (kpc) using cluster redshifts

Masking of invalid or low-coverage regions

2. Compute radial κ profiles & curvature

For each mapmaker × cluster:

Construct azimuthally averaged κ(r)

Apply a stable Savitzky–Golay second derivative filter

Identify curvature extrema and slope changes

Track the physical radius of the curvature “shoulder”

3. Multi–team consistency checks

A genuine astrophysical feature must be shared across mapmakers despite their different modeling assumptions.
The notebook tests this explicitly:

Compare radii of the curvature break for
CATS vs Sharon vs Glafic

Confirm consistency to within statistical variation

Highlight where mapmaker-specific smoothing affects only fine-scale structure, not the shoulder’s location

4. Robustness tests (performed for each mapmaker)

Azimuthal jackknife
Split maps into 4 wedges; the shoulder appears in all wedges.

Centre jitter
Randomise cluster centre within ±2–5 arcsec; radius of the feature remains stable.

Binning / smoothing stability
Test 5–30 kpc radial bins; feature persists across all.

Edge masking
Automatically exclude bins with insufficient azimuthal coverage.

This establishes that the detected feature is not an artefact of any specific pipeline decision.

**Main Empirical Result**

Across all HFF clusters and all three mapmaking teams:

A downward curvature shoulder consistently appears at ∼150–250 kpc (cluster-dependent but tightly grouped).

Agreement across mapmakers is strong evidence that this is:

Not reconstruction noise,

Not a smoothing artefact,

Not a modelling bias (CATS uses parametric + non-parametric, Sharon uses parametric, Glafic uses different assumptions).

The existence of a shared, repeated curvature feature in the outskirts of massive clusters is an observational result, independent of theoretical interpretation.
**License**

MIT License.
CATS, Sharon, and Glafic κ-maps remain the property of their respective authors; only derived quantities appear here.
results used in paper available here: 10.5281/zenodo.17178819.
Feedback to GRTT@axworthy.net 
