# random-darkmatter-micromegas
This repository intends to share the code behind some plots in my publications with an educational purpose.

First, I want to show how to obtain plots in Fig. 16 of the paper [arXiv:2012.11621 [hep-ph]](https://arxiv.org/pdf/2012.11621.pdf).
![Screenshot 2023-02-02 171627](https://user-images.githubusercontent.com/74784192/216380519-e6b51179-1392-4f25-a0b5-ba7255584a1d.png)

### The tools

Tools used to produce this plot:
* [lanhep](https://theory.sinp.msu.ru/~semenov/lanhep.html)
* calchep
* micromegas
* bash-shell scripts
* gnuplot
* a public tool to extract points from plots that I can't remember

### The LanHep part

Well, there was some previous calculations done in Mathematica in order to rotate matrices and get the eigenstates we use to declare the particles in LanHep.
Anyway, the task is not hard. In the folder called lanhep you can find the files we used.
Some interesting points about the lanhep file are:
* We are choosing Feynman gauge: `keys gauge_fixing=Feynman.`
* On line 51 we are declaring the values that we will scan later on `micrOMEGAs`
* On line 179 we declare the scalar content
* On line 324 we add the inert sector Lagrangian
* At the end of the file we are adding `CheckMasses` and `CheckHerm` to run a sanity check

Now having the lanhep model file, the only thing to do is to run in the command line:
> lhep -ca Z2xZ2_3DHM.lhp
