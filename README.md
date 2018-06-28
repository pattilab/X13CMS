# X13CMS
"X13CMS: Global Tracking of Isotopic Labels in Untargeted Metabolomics"

Xiaojing Huang, Ying-Jr Chen, Kevin Cho, Igor Nikolskiy, Peter A. Crawford, and Gary J. Patti
DOI: <a href="http://dx.doi.org/10.1021/ac403384n">10.1021/ac403384n</a>
Analytical Chemistry. 2014
------------------------------------------------------------------------------------------------------------------------------------
## X13CMS 1.4
Installation
````
install.packages("devtools")
library(devtools) 

install_github("pattilab/X13CMS")
library(X13CMS) 
````

Example Files can be downloaded <a href="http://pattilab.wustl.edu/download/Example.zip">here</a>

Changes to v1.4:

- getIsoLabelReport()
1) Default intChoice set to “intb”; was previously “maxo”.
2) Default behavior for enforcing expected monotonic decrease in isotopologue intensity from M0 to Mn in unlabeled samples is to NOT enforce.

- plotLabelReport()
1) Error bars (std dev) are displayed when plotting relative intensity distributions for enriched isotopologue groups.
2) p-value from t-test for difference between total pool size of isotopologue group in unlabeled vs. labeled samples are displayed.
3) Additional arguments required compared to previous version.

- plotIsoDiffReport()
1) Formerly called plotDiffReport(); name changed to avoid confusion with XCMS diffReport()
2) Error bars (std dev) are displayed when plotting relative intensity distributions for enriched isotopologue groups. Groups not enriched in one particular sample class but enriched in the other are plotted only for the enriched class.
3) Additional arguments required compared to previous version.

- plotTotalIsoPools()
1) p-value from t-test for difference between total pool size of isotopologue group in labeled samples of one sample class vs the other are displayed.
2) If an isotopologue group was not significantly enriched in the labeled samples of one sample class, the peak intensities of those isotopologues are plotted anyway, but are indicated as being not significantly enriched.
3) Additional arguments required compared to previous version.

- miniDiffReport()
1) Produces an XCMS diffReport-like table comparing individual features in the unlabeled samples of both sample classes, without the need to re-run xcmsSet() with the sample classes designated as the two biological conditions rather than the labeling type as required for X13CMS

- filterIsoLabelReport()
1) No longer supported

- filterIsoDiffReport()
1) Removed is13C filter

Changes to v1.3:

- getIsoLabelReport():
1) Minor changes to retention time grouping for identifying potential isotopologues
2) Option created for user to enforce expected ion intensity pattern in unlabeled samples (i.e. monotonic decrease from M0 to higher isotopologues)
3) Improved isotopologue grouping for handling redundant peaks returned by XCMS
4) Output report now includes more statistics on both isotopologue peak intensities (standard deviations) and total pool size for each isotopologue group (coefficients of variation for total ion intensity)

- getIsoDiffReport(): Minor changes to output report formatting

- New functions: plotLabelReport(), plotDiffReport(), plotTotalIsoPools() generate pdf files containing plots of all isotopologue groups identified in either a label report of isoDiff report.
