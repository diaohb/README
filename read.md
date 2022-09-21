# README
## Author Zhen Wang (wangz1996@sjtu.edu.cn)

### Compile
To compile the program, cmake (at least 3.11) and gcc (at least 6.2), and maybe some other softwares, are required. So if you are under the ihep server, using the following command to configure environment variables will be convenient:
```bash
    export ATLAS_LOCAL_ROOT_BASE=/cvmfs/atlas.cern.ch/repo/ATLASLocalRootBase
    alias setupATLAS='source ${ATLAS_LOCAL_ROOT_BASE}/user/atlasLocalSetup.sh'
    setupATLAS
    asetup Athena 21.0 latest
```
Now, you can start to compile the program. In the main directory, execute the following command:
```bash
    mkdir build
    cd build 
    cmake ..
    make 
```
### Usage
After compiling, a executable file named hbuana will be generated in bin directory and a shell named setup.sh in build directory. You 
can use the following command to put it in environment variables：
```bash
    source setup.sh
```
Then, you can use the command hbuana anywhere.
#### DAT -> ROOT file (xxx.dat -> Cosmic.root)
```bash
    hbuana -i [path_to_input_file] -o [path_to_output_directory]
```
It only works when both of input file and output directory are specified.
#### ROOT file -> pedestal picture (Cosmic.root -> xxx.png & result.root)
```bash
    hbuana -p list.txt
    hbuana -d list.txt
```
Here, p means pedestal, d means dac, and the content of list.txt is the path of root files. Result.root and some pictures will be generated.
