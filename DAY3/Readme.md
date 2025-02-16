
# DAY3 LAB WORK

## Magic Layout and NGSPICE Characterziation

![image](https://github.com/user-attachments/assets/6af93eab-db17-44dd-aa5d-0e60a65b5ba2)

```
magic -T sky130A.tech sky130_inv.mag &
```

Now we see the Layout of the Inverter. We see the following layers :

```
p-well
n-well
Gate of pmos and nmos are connected to Input pin.
Drain of pmos connected and Drain of nmos are shorted and connected to Output pin.
Source of pmos connected to VDD
Source of nmos connected to VGND
Polysilicon : Red line
```

![image](https://github.com/user-attachments/assets/026d11d5-313a-444e-9cb0-c036c8788d0e)

By selecting usin keyboard key s and typing what in the console we see selected one is polysilicon layer. Connecting Gate of both nmos and pmos.
![image](https://github.com/user-attachments/assets/24419a53-6b2c-4045-8646-b9938b4dee12)

Similar for n-well.
![image](https://github.com/user-attachments/assets/0156dcf0-eedf-4ac7-8b95-effba8978091)

The Technology LEF - It contains information about avialable metal layer via information DRC's of paticular technology used by placer and router etc.

## Standard Cell layout design in Magic
Extracting the details form the layout, parasitics from the cell. 

```
extract all
ext2spice cthresh 0 rthresh 0
ext2spice
```
![image](https://github.com/user-attachments/assets/5f871793-d38d-4858-90fa-fa7b48c95ffc)

![image](https://github.com/user-attachments/assets/edc27b41-e740-4393-a261-e5ad852d2aea)

After opening the extracted spice file.
![image](https://github.com/user-attachments/assets/7604f970-e8de-45cd-807e-07461b4414a3)

Spice file sky130_inv.spice contents. Adding the pmos, nmos model files, Pulse and doing Transient analysis on the inverter.
![image](https://github.com/user-attachments/assets/8bab2ab5-9fe2-4b01-bd09-eb9554d97844)

## NGSPICE 
Loading the skylane130_inv.spice file in ngspice tool.
![image](https://github.com/user-attachments/assets/f4ba2453-d889-4f76-bc40-8a9837bda055)

The Input and Output Waveforms of Inverter
![image](https://github.com/user-attachments/assets/48a0882f-304f-4dc9-81d9-4b477773c036)

![image](https://github.com/user-attachments/assets/cd2dbfc8-c50d-4181-8923-9fea81dc239d)

The basic tr Rise time calculation. 20% to 80% value changes. 
![image](https://github.com/user-attachments/assets/7f60941c-3d6f-448c-854d-c87d6db03797)

The basic tpd Propogation delay. 50% of Output to 50% of input.
![image](https://github.com/user-attachments/assets/5a814374-478c-46f3-a2df-b9e1a060d9cd)

The basic tf Fall time calculation. 80% to 20% value changes.
![image](https://github.com/user-attachments/assets/45a353e0-befe-4438-b3a4-1e2653a5cfea)
