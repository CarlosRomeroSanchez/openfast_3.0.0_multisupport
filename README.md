Modified version OpenFAST v3.0.0
================================

This repository contains a modified version of OpenFAST 3.0.0 in which the Subdyn module has been modified to include the two following features:

-   Multi-support Seismic foundation input motions at the base of the support structure \[1\].
-   A dynamic soil-structure interaction model that employs a Simplified Lumped Parameter Model \[2\] to represent the lateral, vertical, rocking and torsional impedances of the foundation \[3\].

In order to be able to use these features, the following changes have been introduced into the OpenFAST input files:

1.  File *SubDyn.dat*, new line with the variable *SeismicInp*, indicates if there is a seismic signal.
2.  File *SubDyn.dat* includes other new line **Seismic Input File**, read the seismic signal input here.
3.  **Seismic Input File**, in the examples *seismic\_input.dat*.
4.  The *SLPM Coefficients* are indicated in File *SubDyn.dat*, in the line *Simplified LPM-Type members properties*. The SLPM member must have *Flag.1 = SLPM*.

Uniform sismic input motions are assumed (i.e., if there exists more than una support, all of them experience the same foundation input motion). On the other hand, the parameters that define the SLPM must be obtained by fitting the target impedance functions.

The original version of OpenFAST 3.0.0 can be found here [OpenFAST v3.0.0](https://github.com/OpenFAST/openfast/releases/tag/v3.0.0)

\[1\] Romero-Sánchez C. and Padrón L.A., An Implementation of Multi-Support Seismic Input Motion into OpenFAST for the Earthquake Analysis of Offshore Wind Turbines. Computational Methods in Structural Dynamics and Eartquake Engineering, COMPDYN 2023.

\[2\] Carbonari S., Morici M., Dezi F., Leoni G., A lumped parameter model for timedomain inertial soil-structure interaction analysis of structures on pile foundations , Earthquake Engineering & Structural Dynamics, Vol. 47, 2147-2171.(2018)

\[3\] Romero-Sánchez C. and Padrón L.A., Implementation of Ground Input Motion and Dynamic Soil-Structure Interaction into Openfast for the Seismic Analysis of Offshore Wind Turbines. Congress on Numerical Methods in Engineering, CMN 2022.

Financing: 
========
   
This work has been developed with the support of research projects:

* PID2020-120102RB-I00, funded by the Agencial Estatal de Investigación of Spain, MCIN/AEI/10.13039/501100011033.

<p align="center">
   <img src="docs/img/miciinn-aei.png">
</p>

* ProID2020010025, funded by Consejerı́a de Economı́a, Conocimiento y Empleo (Agencia Canaria de la Investigación. Innovación y Sociedad de la Información) of the Gobierno de Canarias and FEDER;

<p align="center">
   <img src="docs/img/gobcan-fse.png">
</p>
