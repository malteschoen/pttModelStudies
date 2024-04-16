# pttModelStudies

## Preamble
In the reposity I wish to compare the effect of several parameters on linear and exponential PTT models.

The parameters varied are:

* Type of model (linear or exponential) (encoded as the first letter - either 0 or 1)
* Zero-shear viscosity (either 333 or 3333) (encoded as the second letter)
* Relaxation time lambda (either 1 or 100) (encoded as the third letter)
* "Elasticity" parameter epsilon (either 0.25 or 0.01) (encoded as the fourth letter)
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

## Sidetrack

It would be quite desirable to be able to know
* the correlation between the Trouton ratio in the deformation-thining and the epsilon parameter
* whether or not epsilons created between the linear and the exponential models translate into each other

## 

## Credits

## References
