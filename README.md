 Hybrid Data 
=================

Introduction
-----------------
This repository provides the evaluation data for the paper submission entitled 
**Programmers Should Still Use Slices When Debugging**. 

We provide the data on 
the evaluation of three major fault localization techniques for a collection of 
74 errors from four open source C projects.


#### Debugging Techniques ####
The evaluated techniques include:
1. **Dynamic Slicing**
2. **Statistical Debugging**, composed of 12 statistical measures:
	- 8 human-generated measures, namely:
		* 5 Optimal/Maximal Measures: `Naish1`, `Naish2`, `Wong1`, `Binary`, `Russel_Rao`
		* 3 Most popular measures: `Ochiai`, `Jaccard`, `Tarantula`
	- 4 Optimal genetically-evolved measures: `GP02`, `GP03`, `GP13` and `GP19`
3. **Hybrid approach** (marriage of both dynamic slicing and Statisical debugging)

#### Subjects ####
The open source C projects making up the subjects in this VM include:
1. **CoREBench**: 37 real open source errors from UNIX utilities, namely `grep`, `coreutils` and `findutils`.
2. **Tcas**: 37 injected errors from the `Siemens and SIR Benchmark`.

#### DataSet ####
This folder contains the dataset for all evaluated techniques, subjects and bugs.
Each folder in */Dataset/`<subject>`/* contains the following information:
1. The pre-processed files in folder  */Dataset/`<subject>`/PreprocessedFiles/* contains: 
	* GDB logs for each execution of the test case
	* The test coverage for each execution of the program
	* The faulty statements obtained from the fix patches for each bug
	* The static slices for each program (and method) in each program
	* The syntactic and semantic call graphs for each program
	* The ranking of each statistical debugging measure
2. For `Tcas` & `Coreutils`, the buggy program in folder */Dataset/`<subject>`/Source/*.

Evaluation Results
---------------------
The *"Results"* folder contains the following:
- **Summary.csv**: details the effectiveness measures of all 74 errors (4 subjects) for 
all three techniques:
	 * statistical debugging - specifically Naish2 statistical measure (header -`Naish2`) 
	 * dynamic Slicing (header - `DynSlicing`)  
	 * hybrid (header - `hybrid`)	 
- **StatisticalDebuggingVsSlicing.csv**: details the effectiveness measures of all 
74 errors (4 subjects) for:
	* all 12 statistical debugging measures - (headers - `Jaccard`, `Tarantula`, `wong1`, `naish2`,`russel_rao`,... )
	* dynamic Slicing (header - `Source-Code Level Slicing`)
- **HybridSensitivityToN.csv**: details the sensitivity of the hybrid approach to 
different values of N (= 2,5,10,15,20,25)
- **Hybrid5 SensitivityToStatisticalDebugging.csv**: details the sensitivity of the hybrid approach 
to different statistical fault localization measures (`Jaccard`, `Tarantula`, `wong1`, `naish2`,`russel_rao`,...)



Virtual Machine
-----------------
**The anonymized version of the Hybrid Virtual Machine would be uploaded soon.**
