
# DAY 2 : LAB WORK
The variables defined for Floorplanning are as shown below : 

![image](https://github.com/user-attachments/assets/6bfc66d3-8ca5-4a43-800b-af128258fee0)

## Floorplan Tcl Script Configuration
The floorplan tcl script used for configuring the simulation. 
![image](https://github.com/user-attachments/assets/d1f55857-dbf4-4d3d-b843-fc4357228485)

```
run_floorplan
```

![image](https://github.com/user-attachments/assets/ffa17e98-b11c-496f-ab06-cefd0ebf979b)

Opening the Magic Tool. The cirrent directory is in <TIMESTAMP>/results/floorplan
```
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/skylane130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def
```

![image](https://github.com/user-attachments/assets/4cc7ae3c-7bf3-4355-8891-88df5caecc2e)

![image](https://github.com/user-attachments/assets/3c1a6a6e-7079-4277-a866-04bd582b4dda)


```
s    - Used to select the object.
v    - center the Die.
what - dispalys the details of the object.
```

In below section shows the object of pins are routed in metal2.
![image](https://github.com/user-attachments/assets/c4f2e828-bc39-4f8d-9295-d60f50eb0b38)

All the logic blocks standard cells are placed in left side corner.
![image](https://github.com/user-attachments/assets/04abd242-3c33-4ebe-aa76-e6cf9dd0f827)

```
run_placement
```

![image](https://github.com/user-attachments/assets/643f2e98-d358-4551-9752-3f5f7b6c5705)

After the command ran : 

![image](https://github.com/user-attachments/assets/cc1e3e66-34d0-4a41-8769-f0776d55e93e)

![image](https://github.com/user-attachments/assets/67ec6809-6107-4a9b-9474-2299e70c2327)

```
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/skylane130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def
```

Opening the Chip after run_placement stage

![image](https://github.com/user-attachments/assets/7b08b12b-c925-4c16-9d3a-0c1e3b3b0cd8)

After every run the screenshot of the result is takenand stored. The View of chip afer this step done is as follws : 

/home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/11-02_14-38/results/placement/picorv32a.placement.def.png


Placement of the Standard cells in Standard rows

![image](https://github.com/user-attachments/assets/899f8bce-75cd-4a48-879b-68402bfbf91b)