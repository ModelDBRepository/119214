# Calcium Calculator Simulation Script Files

The scripts following below reproduce the simulation results presented
in the manuscript (see [Figs. 1-3](http://web.njit.edu/%7Ematveev/documents/figs_TSM_123.pdf)):

|  |
|---|
| [V. Matveev](http://web.njit.edu/%7Ematveev/) , [A. Sherman](http://mrb.niddk.nih.gov/sherman/), [R.S. Zucker](http://mcb.berkeley.edu/faculty/NEU/zuckerr.html), (2002)  <br> **New and Corrected Simulations of Synaptic Facilitation** <br> *Biophysical Journal* **83**:1368-1373. [Full Text](http://www.biophysj.org/cgi/content/full/83/3/1368) [PDF (134 KB)](http://web.njit.edu/%7Ematveev/documents/Matveev_BJ83,1358a.pdf) |

The comments in these script files provide a detailed step-by-step descrption of the corresponding simulations.
All of the files below should be placed in the same subdirectory before running the simulations:

|  |
|---|
| [STF.growth.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/STF.growth.par)  - simulation script calculating the [Ca²⁺] profiles and facilitation growth curves for a five-pulse stimulus train (at 100 Hz), shown in Figs. 1 and 2, B-D.  |

The facilitation decay time courses shown in Fig. 3(B-D) are computed in two stages:

1. [STF.decay.stage1.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/STF.decay.stage1.par) - generates the [Ca²⁺] files corresponding to the different interspike interval values.
2. [STF.decay.stage2.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/STF.decay.stage2.par) - uses the  [Ca²⁺] files created at 1st stage to compute the STF decay time course.

The above scripts rely on (i.e., import) the following scripts describing the model systems of PDEs and ODEs:

A. [quoted.pde.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/quoted.pde.par) - the ***quoted*** parameter set
B. [actual.pde.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/actual.pde.par) - the ***actual*** parameter set
C. [modified.pde.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/modified.pde.par) - the ***modified*** parameter set
D. [tortuosity.pde.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/tortuosity.pde.par) - the parameter set with ***tortuosity***

[XY.ode.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/XY.ode.par) - the script describing the [Ca²⁺] binding scheme ODEs.

---

To reproduce, for example, the Fura-2 curve of Fig. 2 C, execute the following command:

- `calc STF.growth.par C with`

To reproduce the control curve (without Fura) of Fig. 3 D, execute the following two commands (see comments at the beginning of the script for details):

- `calc STF.decay.stage1.par D without 10.0 800.0 25`
- `calc STF.decay.stage2.par D without`

---

**Note for Windows users:** Under Windows, file operations do not default to current directory
(a nuisance!), so make sure that the parameter **path** defined in scripts
[STF.growth.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/STF.growth.par),
[STF.decay.stage1.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/STF.decay.stage1.par) and
[STF.decay.stage2.par](http://web.njit.edu/%7Ematveev/calc/examples/Two_Site_Model/STF.decay.stage2.par) points to the directory where all the script files are residing.

---

<small><a href="http://web.njit.edu/%7Ematveev" target="_top">Victor Matveev</a></small>


This server is running a
[Redhat](http://www.redhat.com/) distribution of
[Linux](http://www.linux.org/).

---
Last modified: Wed Jun 9, 2004

Converted README to Markdown: Mon Jun 2, 2025
