# README
## Author Zhen Wang (wangz1996@sjtu.edu.cn)

### Compile
To compile the program, cmake 3.11 and gcc 6.2, and maybe some other softwares, are required. So if you are under the ihep server, it's
convenient to use the following commend to configure environment variables:
```bash
    export ATLAS_LOCAL_ROOT_BASE=/cvmfs/atlas.cern.ch/repo/ATLASLocalRootBase
    alias setupATLAS='source ${ATLAS_LOCAL_ROOT_BASE}/user/atlasLocalSetup.sh'
    setupATLAS
    asetup Athena 21.0 latest
```
Now, you can start to compile the program. In the main directory, execute the following commend:
```bash
    mkdir build
    cd build 
    cmake ..
    make 
```
### Use
After compiling, a executable file named hbuana will be generated in bin directory and a shell named setup.sh in build directory. You 
can use the following commend to put it in environment variables：
```bash
    source setup.sh
```
Then, you can use the command hbuana anywhere like this:
```bash
    hbuana -p list.txt
```
Here, p means pedestal, and the content of list.txt is the path of root files. After a long time, result.root and some pictures will be generated.





### DAT -> ROOT file (xxx.dat -> Cosmic.root)
    hbuana -i [path_to_input_file] -o [path_to_output_directory]
It only works when both of input file and output directory are specified.
### Analyze ROOT file to make pedestal histogram and trees (Cosmic.root -> result.root)
    hbuana -a [path_to_root_file]
