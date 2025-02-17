
# DAY 4

In Day3 we designed our own Custom Cell from Circuit to Layout design of Inverter. In Magic tool the layout of Inverter was developed. We extracted the parasitics of the Inverter and dumped into spice file. 

## Why ?
The reason is sometimes we do custom cell or group the standard cell and make a logic out of it. During Technology Mapping stage i.e., mapping logic to Standard cells. That is Logic Synthesis and Physical Synthesis step we tend to include the custom designed cell and its layout (FRAM) into our design. Then we proceed further with our Physical Design flow. 

## LAB Work
When we open the pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd. We open the tracks.info file. For this skylane130A the technology node is 130nm and the Fab gives 6 Metal Layers i.e., li1, met1, met2, met3, met4 and met5. So, during routing stage the tool using these metal tracks for routing. 

To explain or understand the concept for example : 
- met1 X 0.17 0.34
- met1 Y 0.17 0.34

The Metal1 track has multiple lines in Horizontal and Vertical layers in chip. The pitch(distance between the two met1 layers in Horizontal and Vertical direction) is 0.34. 

In below snippet it has offset and pitch values. Horizontal track is X and Vertical track Y. 
![image](https://github.com/user-attachments/assets/4d38c0e1-95c1-4d57-97a0-ae1103e7769e)

Now using the li1 information and chnaging the grid information.
![image](https://github.com/user-attachments/assets/ad4a2e0a-d67c-4533-ba65-5723b5f73660)

Dumping the lef file of the standard cell.
![image](https://github.com/user-attachments/assets/50602810-0ea0-410f-931d-7df0de29860a)

Next step is to plug this lef file to our design. We copy the file and move to src directory.
![image](https://github.com/user-attachments/assets/d902ae67-80e9-4e05-9894-7a7ef3924ae0)

Now when we open anyone of our lib file. We see following table 

![image](https://github.com/user-attachments/assets/52ec44bf-eb3c-4496-8705-e0da637afec0)

For timing we have tr, tf and tpd. The chacterization table for each pin and the details.
![image](https://github.com/user-attachments/assets/08f67436-4534-4157-81a8-7fe87e9a973d)

![image](https://github.com/user-attachments/assets/14d36827-2a18-4060-ae96-5db5d4f95410)

For doing STA analysis we generally use the concept of Multi Mode and Multi Corner (MMMC). In our case we have
- skylane130_fd_sc_hd__typical.lib : skylane130_fd_sc_hd__tt_025C_1v80. 
- skylane130_fd_sc_hd__slow.lib  : skylane130_fd_sc_hd__ss_100C_1v60
- skylane130_fd_sc_hd__fast.lib  : skylane130_fd_sc_hd__ff_n40C_1v95

For example the skylane130_fd_sc_hd__<nmos,pmos>_<temp>_<voltage>. 

Copying all the library files to design src folder. 
![image](https://github.com/user-attachments/assets/7ee6eb07-2d51-4bcc-a851-233c97833577)

Now we have lef and timing definition library files included in this.
![image](https://github.com/user-attachments/assets/43ca6a13-4519-4054-86bb-b94a45321ca1)

Updated config.tcl file : 
![image](https://github.com/user-attachments/assets/5e3df8cb-8c70-426b-8aed-fbe35839d161)

Inclusion of Custom cell : 

![image](https://github.com/user-attachments/assets/afd02c3e-eb3c-4029-9626-c490ee2505f2)

![image](https://github.com/user-attachments/assets/031bc3c7-1cf9-4c93-9395-f92cdefc116a)

![image](https://github.com/user-attachments/assets/fb5aa944-2e80-42dc-a692-ac52c872359e)

## Synthesis of including custom cell : 

![image](https://github.com/user-attachments/assets/44cd860f-4e7a-4c54-a9c5-c7e0ad5dcf05)

![image](https://github.com/user-attachments/assets/9d1bf3eb-9391-4a59-8950-74b72d7317c9)

## Placement : 

![image](https://github.com/user-attachments/assets/ee704859-b096-4ad5-a39b-850d8d65f1b4)

![image](https://github.com/user-attachments/assets/6fc1dc7c-392d-41bc-82f6-4b2f4912f80f)

## STA Fixes : Pre-layout Fixes 

### Round 1

![image](https://github.com/user-attachments/assets/1942dd29-9f06-47a9-99c6-1ae264e69795)

### Round 2

![image](https://github.com/user-attachments/assets/9de76430-7fd2-4c46-a83d-3c5fb49fb2c5)

### Round 3

![image](https://github.com/user-attachments/assets/357f3b30-0a92-47ca-92b1-1c61faaaea94)

### Round 4

![image](https://github.com/user-attachments/assets/d77de7f0-1719-473c-bffc-53388e623942)

### Example Sending Fixes

![image](https://github.com/user-attachments/assets/db2a417a-5913-4383-9a36-a3be5838b89d)

![image](https://github.com/user-attachments/assets/32f0a8b1-6d7a-4214-9156-d45273a2a842)

![Uploading image.png…]()


### NOTE 

Give feedback to Logic team to reduce as much as possible because once if you do floorplan, placement. Reduce the setup as much as possible. Next after CTS we will have setup and hold violation also. Make a note of all the fixes sent to folks and send in mail. Add commands also in the mail it becomes easy for them to take in fixes. 

Again, after Routing. The Routing is iterative process again and again it will be done. The fixes can be same(repeated) or different. Sometimes fixes are taken in and some times they are missed. Check with previous reports to newly generated ones. Make a note of all the fixes sent to PnR folks and send in mail. Add commands also in mail it becomes easy for them to take in fixes.  

![image](https://github.com/user-attachments/assets/cadd1cfe-637b-443e-9590-57d9269f4c51)

### Final Fixes

![image](https://github.com/user-attachments/assets/ed8e6846-acfa-4da6-806b-22264af4c9b7)

Next Dump Verilog file : 

![image](https://github.com/user-attachments/assets/54e63e03-2f45-4ed0-82a2-d70626513c20)

![image](https://github.com/user-attachments/assets/406bc012-c879-4623-8839-9a32f41bb2c5)

# Placement 

![image](https://github.com/user-attachments/assets/18eadf10-c2ba-45ee-be5d-c25da2e920a5)

![image](https://github.com/user-attachments/assets/1046bc84-4349-4417-9a5c-87db95eac05b)

![image](https://github.com/user-attachments/assets/41ed189d-eb98-41a6-8328-2897c77e3869)

# CTS 

In the Clock path we have separate Clk Buffer or Clk Inverter cells placed. We have X or H tree from theory in practical or in projects this will be different a little bit. Now in CTS stage onwards will have to focus on Hold time as we did for Setup time. So, many times the fixes given for setup might help or worse the Hold time if path is common. 

In below screenshot you can see the list of cell included are shown below : 

![image](https://github.com/user-attachments/assets/dcc36b75-4b07-41f2-8c37-d475f0eb6bfd)

## Why clk cells ?

Because the clk path needs to have tr = tf.  There needs not be any degradation of the signal on the clk path. 

![image](https://github.com/user-attachments/assets/bdeda28c-95ec-43de-8630-fb785272be6b)

![image](https://github.com/user-attachments/assets/3626bd38-d87f-4983-b27a-169226ef7591)

In CTS insertion of clock cells happen and new netlist is generated. 

![image](https://github.com/user-attachments/assets/512af50f-8016-40ad-875f-7a64abf46371)
