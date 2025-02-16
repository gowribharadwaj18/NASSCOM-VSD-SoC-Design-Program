# DAY 1 : LAB Work
As part of the lab introduction : 

In the Process Design Kits (PDKs) the sky130A folder contains the libs.refs and lib.techs.

## libs.ref
The libs.ref contains the different process folders. In each of these process we have the library (timing corners) , lef files, spice files, mag has the cells shape, the technology lef, the verilog folder has custom defined cell definition using primitive verilog syntax. 

![image](https://github.com/user-attachments/assets/b5198ae1-22b7-4485-b9fd-968a70851651)
![image](https://github.com/user-attachments/assets/2746b90e-6843-44f7-be7b-fc1b2b71f547)

## libs.tech

The libs.tech is the tools folder
![image](https://github.com/user-attachments/assets/c8924444-b4a1-42e7-9404-9af0d81858d2)

![Openlane_Tools](https://github.com/user-attachments/assets/31e8e2a7-e907-452f-969c-e37a21a54ed7)

## Hands On

### Step 1 : 

```
Command Used :
- docker
- ./flow.tcl -interactive
- package require openlane 0.9
```

![image](https://github.com/user-attachments/assets/455f068b-f0eb-4c30-9bcd-0acd290d60c5)

```
prep -design picorv32a
```
When above command is ran you can see the config.tcl used for configuration, PDK's root directory, Standard cell library, LEF files and Metal layers (Only 6 layers are avialble). Then Merging lef (Cell level lef and technology level lef). 

![image](https://github.com/user-attachments/assets/48f57d8a-92d7-47a5-a5d2-8e0b4b59579b)

## Synthesis 

The Synthesis stage generally takes input of the design files (Verilog files), Constraints and Standard cell library (.lib) to generate the Equivalent Logic Circuit. 

Command used for yosys tool : 
```
run_synthesis
```

![image](https://github.com/user-attachments/assets/4ac7a7c9-adfe-4a32-86d8-2ac2942f3d3d)

Results after Synthesis Step is as follows : 

![image](https://github.com/user-attachments/assets/a20b93e3-89b5-46ef-9dda-94c028d4904e)

The Chip area of the chip is 147712.918400.

![image](https://github.com/user-attachments/assets/303b1512-21c4-43f4-a2e5-2d638bd0171a)

# FLOP RATIO

![image](https://github.com/user-attachments/assets/d3a9dff9-4733-4f4d-8ec3-e523f1aa8af9)

The count of D-FF is 1613. 
![image](https://github.com/user-attachments/assets/f7436662-5992-4a4b-88c4-1182a6e88827)

The synthesis netlist generated file as shown below : 
![image](https://github.com/user-attachments/assets/f703d861-0859-4e9d-a6e3-f70464be50d7)

The synthesis reports directory : 
![image](https://github.com/user-attachments/assets/eec868f0-a68a-4a4b-bbbf-8586c8b27599)
