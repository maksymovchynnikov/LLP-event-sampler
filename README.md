# LLP event sampler

## What is it?

This Mathematica code samples the production of various hypothetical long-lived particles (LLPs) and simulates their decays at various experiments located or to be located at different facilities - FNAL, SPS, LHC, FCC-hh. It is a hybrid of [<code>SensCalc</code>](https://github.com/maksymovchynnikov/SensCalc), which calculates the event rate with LLPs without providing a detailed event output, and traditional Monte-Carlo simulators.

## Idea and input

The code uses tabulated LLP angle-energy distribution functions in the form (LLP mass, theta in rad, energy in GeV, distribution function), various experimental setups, and LLP production and decay phenomenology as an input. The distributions may be conveniently generated using <code>SensCalc</code>, while the rest is directly copied from <code>SensCalc</code>.

1. For the given LLP and experiment, it samples 4-momenta of produced LLPs using the admixture of the production channels. To avoid the need to generate a huge statistics for the experiments with small fraction of LLPs reaching the decay volume, the sampling is made only in the direction of the experiment. The absolute yield of LLPs is accordingly generated.

2. Decay vertices of LLPs are sampled within the range of z of the decay volume according to their lifetime. Such sampling allows avoiding generating huge statistics in case of very small or very large lifetimes.   

3. The phase space of LLP's decay products is either simulated on-flight for any mass (for exclusive decays/decays into jets), or precomputed for several masses (for hadronic decays into quarks/gluons where showering and hadronization occurs).

4. The output is a detailed event record containing two files: one about the LLP information - the production yield, the lifetime, the decay probability and decay vertex, and another one about the decay products phase space - the PDG identifier and 4-momentum.

## How to launch

To run the code, two tools have to be installed: [FeynCalc](https://feyncalc.github.io/) and a C compiler. The notebooks should be placed to the <code>SensCalc</code> folder. 

## Status

Early alpha-version.



 
