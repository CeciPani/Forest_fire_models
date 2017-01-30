# Forest fire models simulation code

## Synopsis

This project aim to reproduce the results and the analysis done by Bak et al. and by B.Drossel et al. in their studies of firest-fire models. The forest fire model is defined as a cellular automaton on a LxL grid, this model display self-organized criticality as shown in the analysis of the clusters area of the Drossel model simulations. 


## Usage

This project contains two Jupyter Notebooks for two distinct forest fire models:

* **Forest_fire_model_BAK.ipynb** which contains python code to run simulations of the forest-fire model proposed by P.Bak et al. containing a tree growth rate p and fire spreading to nearest neighbors [("A forest-fire model and some thoughts on turbulence." Phys. Lett. A 147, 297–300)][4].
* **Forest_Fire_Model_DROSSEL.ipynb** which contains python code to run simulations of the forest-fire model proposed by B.Drossel, and F.Schwabl with a lightning probability f [("Self-organized critical forest-fire model." Phys. Rev. Lett. 69, 1629–1632)][3].

Once you run the cell code two directories are created, these will contain all the images created in the simulations. These images are used to create a GIF showing the time evolution of the forest.

The results of the Drossel forest fire model are analysed using *powerlaw* python library. 

## Prerequisites
To create the GIF and to perform the analysis you need to install two python libraries: 
* [images2gif][1]

 ~~~~
 $ pip install -U images2gif
 ~~~~
 In images2gif.py change line 426:
 ~~~~
 for im in images: palettes.append( getheader(im)[1] )
 ~~~~
 to
 ~~~~
 for im in images: palettes.append(im.palette.getdata()[1])
 ~~~~
* [powerlaw][2]

  ~~~~
 $ pip install -U powerlaw
 ~~~~

## Outputs

* Two GIF showing the model time evolution
* One csv file containing simulation results
* One log-log plot of cluster area vs. frequency of cluster area (exponentially truncated power law)





[1]: https://pypi.python.org/pypi/images2gif "images2gif"
[2]: http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0085777 "powerlaw"
[3]: http://journals.aps.org/prl/abstract/10.1103/PhysRevLett.69.1629
[4]: http://162.105.160.8/sys_bio_lib/linux/pdf/1990-21.pdf
