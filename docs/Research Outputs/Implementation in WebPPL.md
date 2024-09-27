[WebPPL](http://webppl.org/) is a probabilistic programming language for the web developed by Noah Goodman et al. that I used to prototyping the implementation of the [QT model](../QT%20Model.md) as a stable version of TreePPL was not available in 2022.  This prototype can be cloned from [https://github.com/vsenderov/qtbirds.webppl](https://github.com/vsenderov/qtbirds.webppl).
## Simulation

Its main usefulness is simulating under [Algorithm 1](../QT%20Model.md#algorithm-1) (`qtbirds-sim.wppl`)—well tested—and [Algorithm 2](../QT%20Model.md#algorithm-2) (`qtbirds-sim2.wppl`)—not so well tested.  You can simulate directly from the command like (see the comments at the top of the file for details):

```
 *   webppl qtbirds-sim.wppl --require fasta2json 
 *                           --require . 
 *                           --require webppl-fs
 *                           --require phyjs -- ...
```

Or, you can [invoke it from Python](Python%20Environment.md).

## Inference

WebPPL can also do sequential Monte-Carlo (SMC) and Markov Chain Monte-Carlo inference, but it is not very performant for our model.  For this reason `qtbirds-inf*` are deprecated as of 2024-09-26.

> [!important] Version
> You should use version sp13.1.0 of qtbirds.webppl (see GitHub tags), as version 14 contains a wrong inference schema.  Either way, you should not use qtbirds.webppl for inference.