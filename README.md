# HPC-Tutorials
- Centralising where I put all my notes, links and basic scripts
- Non-exahustative list of useful tutorials and snippets of code I've found or worked out along for performing Electron Microscopy focused HPC tasks. 

## Useful Links

### General HPC Resources 
- [LLNL](https://hpc.llnl.gov/training/tutorials)
- [NERSC](https://www.nersc.gov/users/training/online-tutorials/)
- [OakRidge NL](https://www.olcf.ornl.gov/for-users/training/)
- [Exascale Computing Project](https://www.exascaleproject.org/all-training-events/)
- [Argone NL](https://www.alcf.anl.gov/support-center/training-overview)
- [UCI](https://hpc.oit.uci.edu/)
### Schedulers
- [Slurm](https://slurm.schedmd.com/tutorials.html)
- [SGE (Son of Grid Engine)](https://arc.liv.ac.uk/SGE/)

### File Systems *(probably not useful)*
- [BEEGFS](https://www.beegfs.io/wiki/FAQ)

## Code Snippets

### Run a Jupyter noteboook (you can subsitute jupyter notebook for jupyter lab)
**This is in the clear, so may not be the best way to do this.... but its tunneled through SSH so maybe fine, alex check this**
*A lot of this will depend on the exact config of your HPC networks, and there are a number of alterantive ways to do this*

#### Login node
1. On local machine, Login to the HPC `ssh <username>@hpc.domain`
2. On HPC, Start a Jupyer notebook `jupyter notebook --no-browser --port=<port_number>` *port_number is 4 digits, avoid picking the standard 8888 port*     
This Produces a token of the type `http://127.0.0.1:<port_number>/?token=<alpha-numeric characters>`
*If you pick an already in use port the HPC will try different ones, make a note of the actual port number it is running on
3. On local, In a separate terminal create your ssh tunnel 
`ssh -NL LocalHost:port_number:LocalHost:port_number <username>@hpc.domain`
4. On local, copy the token `http://127.0.0.1:<port_number>/?token=<alpha-numeric characters>` from the HPC terminal into your local browser. 

#### Compute node
1. On local machine, login to the HPC `ssh <usename>@hpc.domain`
2. On HPC, get an interactive session e.g. in slurm `srun <your compute needs, parition etc.>
3. On HPC interactive node, make a note of the compute note you assigned, you can run `hostname` to double check 
4. On HPC interactive node, start a jupyter notebook `jupyter notebook --no-browser --port=<port_number> --ip=$(hostname)`
This Produces a token of the type `http://127.0.0.1:<port_number>/?token=<alpha-numeric characters>`
5. On local machine in a separate terminal create you ssh tunnel 
`ssh -NL port_number:hostname:port_number <username>@hpc.domain`
6. On local, copy the token `http://127.0.0.1:<port_number>/?token=<alpha-numeric characters>` from the HPC terminal into your local browser.


  

### Various Bash Commands



## To Do List:

- [ ] Check the jupyter notebook security aspect (check with NERSC and UCI see what they say)
- [ ] Add bash aliases to improve the jupyter notebook 
- [ ] Go through my bash cheat sheet and start adding commands
- [ ] Organise the bash commands in to logical headings, e.g. job submission, file admin, etc.   
