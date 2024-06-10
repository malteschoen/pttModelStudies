## Mission statement
In the reposity I wish to compare the effect of several parameters on linear and exponential PTT models.

The parameters varied are:

* Type of model (linear or exponential or Giesekus) (encoded as the first letter - either 0,1 or 2)
* Zero-shear viscosity etaZero (either 333 or 3333) (encoded as the second letter)
* Relaxation time lambda (either 1 or 0.01) (encoded as the third letter)
* "Elasticity" parameter epsilon (either 0.25 or 0.01 for the PTT models and either 0.01 or 0.5 for the Giesekus models) (encoded as the fourth letter)
* "Affinity" parameter zeta (0 or 0.03) (encoded as the fifth letter)

I intend to create combined curves featuring

* Shear viscosity as a function of shear rate
* Elongational viscosity as a function of elongation rate
* Normal
* First normal stress difference as a function of shear rate
* Shear stress during start-up
* Elongational stress during start-up
* Theoretical (!) molecular weight distribution

## Caveats
* For real simulation, you'll probably want to run a multimode PTTLog model
* As of right now I really have no idea how well epsilon from the current non-logarithmic model maps to the epsilon used in those models

## Terminology & theory
- ToDo: A brief excursion into Mendelsons simple model of die swell.


## Linear or exponential model?
![linPttVersusExpPTT_elongational](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/001a_linPTT_versus_expPTT.png)

The picture above shows that the linear PTT model has a major drawback: the steady-state uniaxial elongational viscosity (blue solid line) remains constant for elongational rates past the Newtonian plateau. This is difficult to reconcile with other works on steady-state uniaxial elongational viscosity.

![linPttVersusExpPTT_swell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/001b_linPTT_versus_expPTT.png)

The picture above is even more damning: the linear PTT model predicts progressively growing die swell (blue dotted line) past the Newtonian plateau. Reality has so far completely refused to adhere to this model. 

## Effect of zero-shear viscosity in the exponential model

![etaZeroViscosity](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/004a_effect_of_etaZero.png)

The picture above shows that the zero-shear viscosity shifts the curves 'up and down'.

![etaZeroSwell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/004b_effect_of_etaZero.png)

The picture above shows that the zero-shear viscosity has no effect on die swell.

## Effect of relaxation time lambda in the exponential model

![lambdaViscosity](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/003a_effect_of_lambda.png)

The picture above shows that the relaxation time lambda shift the curves 'left to right'.

![lambdaSwell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/003b_effect_of_lambda.png)

The picture above shows that the relaxation time lambda shift the curves 'left to right'.

## Effect of elasticity parameter epsilon in the exponential model

![epsiViscosity](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/002a_effect_of_epsilon.png)

The picture above shows that with lower value of the elasticity parameter epsilon, steady-state uniaxial elongational viscosity exceeds steady-state shear viscosity by a larger factor (higher Trouton ratio).

![epsiSwell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/002b_effect_of_epsilon.png)

The picture above shows that epsilon also has an outsized effect on die swell.

## Effect of affinity parameter zeta in the exponential model

![zetaViscosity](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/005a_effect_of_zeta.png)

The picture above shows that with higher value of the affinity parameter zeta, the shear-thinning becomes more pronounced. The behaviour shown is highly unlikely to be observed in thermoplastic melt.

![zetaSwell](https://github.com/malteschoen/pttModelStudies/blob/main/newPictures/005b_effect_of_zeta.png)

The picture above shows that with higher value of the affinity parameter zeta, die swell turns really really weird.


## ToDos

It would be quite desirable to be able to know
* the correlation between the Trouton ratio in the deformation-thining and the epsilon parameter
* whether or not epsilons created between the linear and the exponential models translate into each other

## Constitutive equations

## References
