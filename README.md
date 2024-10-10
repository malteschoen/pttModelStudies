## Chapter 0: Table of contents: 
* Chapter 1: Mission statement
* Chapter 2: Linear, exponential or generalised Mittag-Leffler model?
* Chapter 3: Effect of zero-shear viscosity in the exponential model
* Chapter 4: Effect of relaxation time lambda in the exponential model
* Chapter 5: Effect of elasticity parameter epsilon in the exponential model
* Chapter 6: Effect of affinity parameter zeta in the exponential model
* Chapter 7: Heuristics for an initial guess of epsilon in the exponential model
* Various appendices
* References

## Chapter 1: Mission statement

In this reposity I wish to compare the effect of several parameters of different PTT models on melt properties relevant to engineering work.

<details>
<summary>[CLICK TO EXPAND AND VIEW] </summary>

 
### Parameters varied are:

* Type of model (linear or exponential or Giesekus or generalised Mittag-Leffer) (encoded as the first letter - either 0,1,2,3)
* Zero-shear viscosity etaZero (either 333 or 3333) (encoded as the second letter)
* Relaxation time lambda (either 1 or 0.01) (encoded as the third letter)
* "Elasticity" parameter epsilon (either 0.25 or 0.01 for the PTT models and either 0.01 or 0.5 for the Giesekus models) (encoded as the fourth letter)
* "Affinity" parameter zeta (0 or 0.03) (encoded as the fifth letter)

I intend to create combined curves featuring

* Shear viscosity as a function of shear rate
* Elongational viscosity as a function of elongation rate
* First normal stress (difference) as a function of shear rate
* Shear stress during start-up
* Elongational stress during start-up
* Theoretical (!) molecular weight distribution

### Caveats
* For real simulation, you'll probably want to run a multimode PTTLog model
* As of right now I really have no idea how well epsilon from the current non-logarithmic model maps to the epsilon used in those models

### Approximation of die swell
See [this link](https://github.com/malteschoen/rheologyHacks#chapter-4-a-simple-formula-for-shear-induced-die-swell) for the formula used to approximate die swell.
</details>

## Chapter 2: Linear, exponential or generalised Mittag-Leffler model?
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>
 
![linPttVersusExpPTT_elongational](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/001a_linPTT_versus_expPTT.png)


The picture above shows that the linear PTT model has a major drawback: the steady-state uniaxial elongational viscosity (blue solid line) remains constant for elongational rates past the Newtonian plateau. This is difficult to reconcile with other works on steady-state uniaxial elongational viscosity.


![linPttVersusExpPTT_swell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/001b_linPTT_versus_expPTT.png)

The picture above is even more damning: the linear PTT model predicts progressively growing die swell (blue dotted line) past the Newtonian plateau. Reality has so far completely refused to adhere to this model. 

**So, is the exponential PTT model suitable in any case?**
* Well, it is, with one exception that might or might not affect your use case. I am talking about the fact that in both linear and exponential PTT model the slope of the viscosity in the decades beyond the transitional region is 'hard-coded' (to a value of 45 degrees in the log-log-plot).
* In more mathematical terms: The Carreau parameter C is locked at at 1, the power-law coefficient is fixed at n = 0.5
* For reference, the melts of most commercial polymers have power-law coefficents above 0.5 in their 'terminal shear-thinning region'. Some other materials (including rubbers) exhibit 'terminal power-law coefficients' as low as 0.2.
* The generalised Mittag-Leffler PTT model affords us the option of varying the 'terminal viscosity slope'. Its parameters are described in more detail in chapter 8 to 12.
* Still, real engineering data on shear viscosity very rarely covers multiple decades in the shear-thinning region since an engineer is unlikely to encounter an application in which multiple decades of shear rate are present AND relevant at the same time.
* Hence it is often possible to achieve a good curve fit by changing the relaxation time lambda.
* This then leads to 'unphysical' values of lambda. As lambda mostly impacts transient behaviour, many steady-state extrusion processes can still be modelled well.
* However, if accurate understanding of transient behaviours (and the underlying molecular stress/relaxation state) is crucial, this kind of manipulation should be avoided.
* In conclusion, some indications and contraindications for usage of Mittag-Leffler PTT model in place of an exponential PTT model can be given.
  * Indications
     * tba
     * tba
  * Contraindications
     * tba
     * tba
       
Finally, contraindications against the use of **any** PTT model are
  * Presence of a second Newtonian plateau (e.g. very highly filled materials, polymer solutions)
  * to be added

</details>

## Chapter 3: Effect of zero-shear viscosity in the exponential model
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>
 
![etaZeroViscosity](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/004a_effect_of_etaZero.png)

The picture above shows that the zero-shear viscosity shifts the curves 'up and down'.

![etaZeroSwell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/004b_effect_of_etaZero.png)

The picture above shows that the zero-shear viscosity has no effect on die swell.
</details>

## Chapter 4:  Effect of relaxation time lambda in the exponential model
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>
 
![lambdaViscosity](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/003a_effect_of_lambda.png)

The picture above shows that the relaxation time lambda shift the curves 'left to right'.

![lambdaSwell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/003b_effect_of_lambda.png)

The picture above shows that the relaxation time lambda shift the curves 'left to right'.
</details>

##  Chapter 5: Effect of elasticity parameter epsilon in the exponential model
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>
 
![epsiViscosity](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/002a_effect_of_epsilon.png)

The picture above shows that with lower value of the elasticity parameter epsilon, steady-state uniaxial elongational viscosity exceeds steady-state shear viscosity by a larger factor (higher Trouton ratio). Also, a careful viewer will have observed that smaller value of epsilon appears to shift the curves towards higher deformation rates. See Appendix 1 for more details on this.

![epsiSwell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/002b_effect_of_epsilon.png)

The picture above shows that epsilon also has an outsized effect on die swell.
</details>

##  Chapter 6: Effect of affinity parameter zeta in the exponential model
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>
 
![zetaViscosity](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/005a_effect_of_zeta.png)

The picture above shows that with higher value of the affinity parameter zeta, the shear-thinning becomes more pronounced. The behaviour shown is highly unlikely to be observed in thermoplastic melt.

![zetaSwell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/005b_effect_of_zeta.png)

The picture above shows that with higher value of the affinity parameter zeta, die swell turns really really weird.
</details>

## Chapter 7:  Heuristics for an initial guess of epsilon in the exponential model
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>
 
* We can provide two simple  of thumb for a initial guess of epsilon based on the interrelation of epsilon and the uniaxial Trouton ratio Tr.
* Tr is defined as the ratio of uniaxial elongational viscosity and shear viscosity at a certain deformation rate - in the Newtonian plateau Tr is 3, meaning that differences become only visible with higher deformation rates.
 * We've generated the dataset for deformation rates of 100/s which should lie in the shear-thinning domain of most materials, while at the same time being accessible to both rotational and capillary rheometers.
* Please note that an elongation rate of 100/s requires higher shear rates in capillary rheometers -(around 450 1/s for the standard HPCR with a 15 mm barrel feeding a 1 mm capillary).Refer to [my work](https://github.com/malteschoen/fasterGibsonForExtensionalFlowBetweenCapillaries) on the (simplified) Gibson method for more details.
* Users of rotational rheometers should endeavour to either measure or approximate the normal stresses. See [my work](https://github.com/malteschoen/rheologyHacks) on rheological formulae for more details.
  
![epsilonFromTrouton](https://github.com/malteschoen/pttModelStudies/blob/main/expModelEpsilonTroutonStudies/epsilonFromTroutonRatio.png)

The first heuristic follows a power law of $\epsilon = 11 (Tr^{\frac{20}{11}})$ , while the second heuristic is a very simple (yet surprisingly useful) rule of thumb of $\epsilon = \frac{1}{Tr}$

![epsilonFromPSI1](https://github.com/malteschoen/pttModelStudies/blob/main/expModelEpsilonTroutonStudies/epsilonFromPSI1.png)

Similarly, a power law can be constructed for PSI1, the first normal stress coefficient. 

</details>

## Appendix 1: The interaction between $\epsilon$ and $\lambda$ 
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>

Traditionally, the inverse of the relaxation time lambda has been interpreted as 'a critical deformation rate at which interesting things happen'. These interesting things are:
- For a plot of steady-state shear viscosity over shear rate, the inverse of the relaxation time lambda (or B, if a Carreau-style model is employed) is the critial shear rate $\dot{\gamma}_{crit}$ that delineates the (first) Newtonian plateau region and the shear-thinning region. If extrapolations from both regions are made (which are straight lines in the log-log plot yet follow power-law equations), the intersection point is found at the critical shear rate, which is 1/lambda.
- For a plot of steady-state elongational viscosity over elongation rate, the global maximum of the elongational viscosity is found for a critical elongation rate $\dot{\epsilon}_{crit}$ of 1/lambda.

Chapter 4 neatly illustrates this effect.

If you now observe the results of chapter 5 instead, you will note that smaller value of epsilon appears to shift the curve towards higher deformation rates. In effect, the critical deformation rate is shifted. 
This effect can be expressed (and corrected for) using the following formulae:

$\dot{\gamma}_{crit} = \frac{1}{\lambda\sqrt{\epsilon}}$

$\dot{\epsilon}_{crit} = \frac{1}{\lambda\sqrt{\epsilon}}$


I recall at least one paper also applying this correction in discussing a curve of viscosity over deformation rate, yet cannot seem to recover that paper. It will be added in due time.

For the moment, I refer to [3](https://doi.org/10.1017/S002211209900453X), who use a dimensionless group of
$De \sqrt{\epsilon} = \lambda \frac{U}{H} \sqrt{\epsilon} = \lambda \dot{\gamma}\sqrt{\epsilon}$

which can be recast to this:

$\dot{\gamma}_{crit} = \frac{1}{\lambda\sqrt{\epsilon}}$

For a scientist interested in intuiting and comparing the PTT model or an engineer tasked with relating model parameters to existing data, I leave the note that you should consider the 'real relaxation time' of a PTT fluid to be $\lambda\sqrt{\epsilon}$. This 'real relaxation time' can be meaningfully compared to relaxation times found in measurements data and other models.
</details>


## Appendix 2: ToDos
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>
 
* It would be quite desirable to be able to know
    * the correlation between the Trouton ratio in the deformation-thining and the epsilon parameter
    * whether or not epsilons created between the linear and the exponential models translate into each other

* Write out the full constitutive equation of the exponential PTT model, simplify to an explainable level
 
</details>





## References
<details>
<summary> [CLICK TO EXPAND AND VIEW] </summary>
[1]  where did it go?
 
[2]  Mendelson, R. A. ; Finger, F. L. ; Bagley, E. B.: Die swell and recoverable shear strain in polyethylene extrusion.  Journal of Polymer Science Part C: Polymer Symposia 35 (1971) 1, p. 177–188 - DOI: 10.1002/polc.5070350114

[3]  Oliveira, Paulo J. ; Pinho, Fernando T.: Analytical solution for fully developed channel and pipe flow of Phan-Thien–Tanner fluids. In: Journal of Fluid Mechanics Bd. 387 (1999), S. 271–280 - DOI: 10.1017/S002211209900453X

</details>
