---
# NASSCOM_VSD (Digital VLSI SoC Design and Planning)
![WhatsApp Image 2024-09-16 at 1 29 52 AM](https://github.com/user-attachments/assets/55ebd9bc-857a-4509-8a5d-1c54aa5cfbfd)
---
---
# #LAB-1
---
## 1] Run 'picorv32a' design synthesis using OpenLANE flow.

### Steps for Implementation

1. #### Go to Virtual Machine & Open the Terminal
2. #### Navigate to the Openlane Directory
   > cd Desktop/work/tools/oplane_working_dir/openlane
3. #### Start Docker
   > docker
4. #### Run Openlane in Interactive Mode
   > ./flow.tcl -interactive
5. #### Input the required packages for proper functionality of the OpenLANE flow
   > package require openlane 0.9

##### Screenshots of running each commands
![Screenshot 2024-09-09 092240](https://github.com/user-attachments/assets/4b2a98ed-d017-4356-b2db-f16f9e25eb84)
---
6. #### To run any design and initially we have to prep the design creating some necessary files
   > prep -design picorv32a

![Screenshot 2024-09-09 093606](https://github.com/user-attachments/assets/d20f21df-a853-40dd-9890-0894e5694285)

7. #### Then Run Synthesis using following command
   > run_synthesis

![Screenshot 2024-09-09 094316](https://github.com/user-attachments/assets/bd3c4df3-b9ba-4378-9767-34db57e39596)

## 2] Calculate the Flop Ratio.

### Screenshots of Calculation:
![Screenshot 2024-09-09 095805](https://github.com/user-attachments/assets/82fcfd22-a746-4e74-b408-294b0c009517)

1. Flop Ratio:

```math
Flop\ Ratio = \frac{Number\ of\ D\ Flip\ Flops}{Total\ Number\ of\ Cells}
```
   That is:

```math
Flop\ Ratio = \frac{1613}{14876} = 0.108429685


```
2. Percentage of DFF's:

```math
Percentage\ of\ DFF's = Flop\ Ratio * 100
```
   That is:

```math
Percentage\ of\ DFF's = 0.108429685 * 100 = 10.84296854\ \%
```
---
# #LAB-2
---
## 1] Run 'picorv32a' design floorplan using OpenLANE flow.
### Steps for Implementation

1. #### Go to Virtual Machine & Open the Terminal
2. #### Navigate to the Openlane Directory
   > cd Desktop/work/tools/oplane_working_dir/openlane
3. #### Start Docker
   > docker
4. #### Run Openlane in Interactive Mode
   > ./flow.tcl -interactive
5. #### Input the required packages for proper functionality of the OpenLANE flow
   > package require openlane 0.9
6. #### To run any design and initially we have to prep the design creating some necessary files
   > prep -design picorv32a
7. #### Then Run Synthesis using following command
   > run_synthesis
8. #### Now run the floorplan
   > run_floorplan
![floorplan_succ](https://github.com/user-attachments/assets/af6ad693-a836-4aa5-8b1c-90cdf3c93b27)

## 2] Load generated floorplan def in magic tool and explore the floorplan.
### Steps for Implementation

1. #### Change directory to path containing generated floorplan def
   > cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/15-09_09-41/results/floorplan/
2. #### Command to load the floorplan def in magic tool
   > magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
   ![magic1](https://github.com/user-attachments/assets/5d42eb30-2f3e-41e5-9cbe-36890db3f73e)

3. #### Equidistant placement of ports
   ![magic2](https://github.com/user-attachments/assets/e49dd312-3752-4a55-a12f-eead8e03eece)
![what1](https://github.com/user-attachments/assets/ea231d35-73d3-4b4a-8ea4-d5d99eef82bb)
![wht2](https://github.com/user-attachments/assets/64ad40a0-ded7-4284-9e8b-397de40321da)
![what3](https://github.com/user-attachments/assets/caefaff2-9c71-4324-83f8-d4cae6c9b636)

4. #### Command to run placement
   > run_placement
   ![placement1](https://github.com/user-attachments/assets/2353596d-4828-4ff2-b90a-7d9f349f0553)
![placement3](https://github.com/user-attachments/assets/64b6540e-8d50-497b-b1bf-27d939bf66c2)

5. #### Load generated placement def in magic tool.
   > cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/15-09_09-41/results/placement/

6. #### Command to load the placement def in magic tool
   >magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
   ![mag3](https://github.com/user-attachments/assets/e27c37aa-2d55-42ee-8118-46309890f41e)
![mag4](https://github.com/user-attachments/assets/3b0c30ff-fa79-4b95-9410-f75d6bf455c8)
---
# #LAB-3
---
## 1] Clone custom inverter standard cell design from github repository

1. #### Change directory to openlane
> cd Desktop/work/tools/openlane_working_dir/openlane

2. #### Clone the repository with custom inverter design
> git clone https://github.com/nickson-jose/vsdstdcelldesign

3. #### Change into repository directory
> cd vsdstdcelldesign

3. #### Copy magic tech file to the repo directory for easy access
> cp /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech .

4. #### Check contents whether everything is present
> ls

5. #### Command to open custom inverter layout in magic
> magic -T sky130A.tech sky130_inv.mag &

. Screenshot of commands run
![1](https://github.com/user-attachments/assets/dd3fd22c-d78a-48a9-ab90-8bf4a4a093bc)

## 2] Load the custom inverter layout in magic.

1. #### Load Magic
![2](https://github.com/user-attachments/assets/4d14f5dc-750a-4b9c-a087-773767ee3df8)


2. #### NMOS and PMOS identified
![3_nmos](https://github.com/user-attachments/assets/d788757c-7798-4978-ac75-74a27426126d)
![4pmos](https://github.com/user-attachments/assets/306bf983-52bf-484b-b9b2-6cb0afc73582)


3. #### Output Y connectivity to PMOS and NMOS drain verified
![5output](https://github.com/user-attachments/assets/d1a5a5bb-decb-4da9-9276-4337323a7e4b)


4. #### PMOS source connectivity to VDD (here VPWR) verified
![Screenshot from 2024-09-15 15-46-06](https://github.com/user-attachments/assets/916ef186-f848-44c0-af3d-46c0ebc7817a)

5. #### NMOS source connectivity to VSS (here VGND) verified
![7](https://github.com/user-attachments/assets/0a429698-8102-48a9-a995-00dfe91adead)

## 3] Spice extraction of inverter in magic.

1. #### Commands for spice extraction of the custom inverter layout to be used in tkcon window of magic
```bash
pwd
extract all
ext2spice cthresh 0 rthresh 0
ext2spice
```
![8](https://github.com/user-attachments/assets/7b594e59-ae27-4327-bfe8-893cac6a4f27)

2. #### Create spice file
![10](https://github.com/user-attachments/assets/f9014a72-76dc-487c-9f36-9ea25fda5299)

3. #### Measure unit distance in layout grid
![11](https://github.com/user-attachments/assets/8254636a-bc06-47e5-a401-b1a207ae86e5)

4. #### Simulat & Download ngspice
![13](https://github.com/user-attachments/assets/1e226fe7-55c4-4cd7-b2ae-cef60f2eb9a2)
![ngspice2](https://github.com/user-attachments/assets/d68969b2-ba73-4fa4-b4fe-037200f62a24)

5. #### Calculate Rise Time: Subtract the time at 10% from the time at 90% to get the rise time.

            Rise Time = T80%−T20%
            80 % of 3.3V is 2.64 
            20 % of 3.3V is 0.66

![80%2 64command](https://github.com/user-attachments/assets/a2798e96-b320-4ff2-ac22-890aebf1efe9)
1) 80 Percent of 3.3V is 2.64
![80%2 64](https://github.com/user-attachments/assets/ae4da3fb-4428-48bd-ac9b-dd2e25cd4f9a)
2) 20 Percent of 3.3V is 0.660
![20%660](https://github.com/user-attachments/assets/aabe8117-a89c-4bce-8c81-1c50cb7280b1)
3) Rise Transition time = 6.16096 - 4.03964  = 2.12132ps
 ![Screenshot 2024-09-16 220720](https://github.com/user-attachments/assets/1a4dc54b-4572-4a56-808a-a4a0aea6c412)

6. #### Calculate Fall Time: Subtract the time at the 80% point from the time at the 20% point.

            Fall Time= T80% − T20% =  2.09-2.03  = 0.03 = 30ps
   
   1) 80 Percent of 3.3V is 2.64
   ![80%fall](https://github.com/user-attachments/assets/e39018b2-8c1f-42db-88cd-73b473769125)
   2) 20 Percent of 3.3V is 0.660
   ![20%660fall](https://github.com/user-attachments/assets/4831e9c7-49e7-4f5a-96ce-80149aa97cd8)

7. #### Rise Cell Delay :
   
   ```bash
       Rice Cell Delay= Tout50%​ − Tin50%​
       Rice Cell delay =  2.12414 - 2.06000 =  0.06414 = 64.14ps
      ```
   ![Screenshot 2024-09-16 222657](https://github.com/user-attachments/assets/001c3383-05fe-41de-ab1a-8ff9e9d6fff0)
   ![Screenshot 2024-09-16 223242](https://github.com/user-attachments/assets/0c93a488-97b3-45d4-bfd9-f1e22aecce69)

8. #### Fall Cell Delay :
   ```bash
   Fall Cell Delay = Tout 50% - Tin 50%
                         = 4.02667 - 4.00483 
                         = 0.02184
                         = 21.84 ps
   ``` 
   ![Screenshot 2024-09-16 223335](https://github.com/user-attachments/assets/b992d226-3857-4b38-89e0-889872a74cf1)
   ![fall cell dealy calcylatin orignal ](https://github.com/user-attachments/assets/de343014-ee65-4e28-bcc7-c6889a0d4c09)

## 4] Steps to magic and Steps to load sky130 tech-rules
   
      1.  Go to home directory
      2.  download the lab files
              wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
      3. extract it
              tar xfz drc_tests.tgz
      4. Go to - cd drc_tests
      5. to view .magicrc file
         command : gvim .magicrc
      6. Command to open magic tool in better graphics ->  magic -d XR &
   

   ![Screenshot 2024-09-16 225308](https://github.com/user-attachments/assets/7b702876-24d2-4bc3-bba4-0f6911757733)
   ![Screenshot 2024-09-16 225518](https://github.com/user-attachments/assets/8ff499e6-eb9f-4d6e-b4e7-735bbee86547)

#### Load Poly
![Screenshot 2024-09-16 225649](https://github.com/user-attachments/assets/390c0125-ec20-45af-acb4-709c3761530f)

## 5] To fix poly.9 and change it.

            Poly resistor spacing to poly or spacing (no overlap) to diff/tap   0.480µm
            poly.9 rule no drc violation even though spacing < 0.48u

![Screenshot 2024-09-16 225947](https://github.com/user-attachments/assets/626d9a34-97be-4ffc-9087-b7cd23e1317d)
![Screenshot 2024-09-16 230041](https://github.com/user-attachments/assets/6df9719c-8799-404f-8411-21e3c8c0817d)

## 6] Commands to run in tkcon window
       
       1. To Load updated tech file
        -> tech load sky130A.tech

        2. re-run drc check to see updated drc errors
        -> drc check

        3. Selecting region displaying the new errors and getting the error messages 
        -> drc why
        

![Screenshot 2024-09-16 230444](https://github.com/user-attachments/assets/6b7b0e84-1b07-4766-9d75-f648660994e4)

---
# #LAB-4
---
## 1] Generate lef from the layout.
 
 ### 1st Condition : The input and output ports of the standard cell should lie on the intersection of the vertical and horizontal tracks.
1. tracks.info of sky130_fd_sc_hd
![sky_130A_track_info](https://github.com/user-attachments/assets/5115610c-e9c7-495f-b3b2-077c6baeedd4)

2. tkcon window to set grid as tracks of locali layer
![grid_command_terminal](https://github.com/user-attachments/assets/fe126ea2-2f7c-4abf-a80f-6857a3687a9a)

3. input and output ports of the standard cell should lie on the intersection of the vertical and horizontal tracks.
![after_grid](https://github.com/user-attachments/assets/32f79c44-dab1-4e4c-819b-b8f4be85cb2f)


### 2nd Condition : width of the standard cell must be odd multiple of the xpitch or xdirection.
Width of standard cell = 1.38 um = 0.46 ∗ 3 
![horizontal_width](https://github.com/user-attachments/assets/215b233b-c51b-4839-8bcd-a74ac8072ea2)


### 3rd Condition : Hight of the standard cell must be even multiple of the ydirection or ypitch
Height of standard  cell = 1.38 um = 0.46 ∗ 3 
![vertical_height](https://github.com/user-attachments/assets/f70e95a7-7c17-48a8-a4f0-55a26be88107)


## 2] Defining the Port 
![A_locali](https://github.com/user-attachments/assets/2a38a90c-b100-4b09-8b61-f951e7e7ac34)
![y_locali](https://github.com/user-attachments/assets/c9b6dd3d-4105-4a11-935e-fd51c28e53ac)
![vPWR](https://github.com/user-attachments/assets/7f1f2a34-2a7c-4531-920b-ec20da9b309d)
![VGND](https://github.com/user-attachments/assets/44181246-dc51-4f5a-a4f0-118068f6b8ee)

1. NEW Layout Created
![new_mag](https://github.com/user-attachments/assets/215484a3-ae96-455e-8bc7-2a390840e140)

 2. tkcon window to save the layout with custom name and new lef file
 ![lef_write_with all](https://github.com/user-attachments/assets/0147b96b-a224-4b31-9e40-54cf6bdfa200)

3. Introduction to timing libs and steps to include new cell in synthesis
1) Copy the new lef file to
> /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
2) Copy lib files
> "sky130_fd_sc_hd.lib" from vsdstdcelldesign/lib to /Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/


4. #### Edit 'config.tcl' 
```blash
  	set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
	set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
	set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
	set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

	set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]
 ```

 ![configedit](https://github.com/user-attachments/assets/79774496-72b2-45c5-a62d-adc537ff2ab5)

5. #### openlane flow synthesis with newly inserted custom inverter cell.
```blash
	steps
 	1. go to openlane directory : cd Desktop/work/tools/openlane_working_dir/openlane
  	2. docker
   	3. ./flow.tcl -interactive
    	4. package require openlane 0.9
        5. prep -design picorv32a -tag 11-09_16-08 -overwrite
	6. set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
 	7. add_lefs -src $lefs
  	8. echo $::env(SYNTH_STRATEGY)
   	9. set ::env(SYNTH_STRATEGY) "DELAY 3"
    	10. echo $::env(SYNTH_BUFFERING)
     	11. echo $::env(SYNTH_SIZING)
      	12. set ::env(SYNTH_SIZING) 1
        13. echo $::env(SYNTH_DRIVING_CELL)
	14. run_synthesis
	15. run_floorplan 
 		we will get error after error 
   		1. init_floorplan
     		2. place_io
       		3. tap_decap_or
	 16 run_placement
  	17 magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```

![synth_overwrite](https://github.com/user-attachments/assets/f4f8f5be-b54d-4143-ab1f-0f3e036b5e02)

1) total negative slack =-711.59   and wrost negative slack = -23.89.
![synthesis completed](https://github.com/user-attachments/assets/d8945cb4-4dc1-4024-848e-440913c13368)

 2) after this performed steps are from 5 to 14 
 ![zero _negative slack](https://github.com/user-attachments/assets/45ff0442-cc79-43da-ac51-0054f022661c)

3) Now we got TNS and WNS = 0

4) Now we perform floorplan 
> run_floorplan
 ![run_floorplan](https://github.com/user-attachments/assets/211c24f8-2bf4-432d-8621-53b3a68b92df)
![error](https://github.com/user-attachments/assets/d0a4d661-c330-4897-9581-4db4c9b6dc65)

5) after getting error run following commands
```blash
	1. init_floorplan
	2. place_io
	3. tap_decap_or
```

![init_floorplan](https://github.com/user-attachments/assets/7dd207eb-cdc5-46f3-a72c-9aacd4550f01)
![tap_decap](https://github.com/user-attachments/assets/4197501d-032c-4f80-9959-ca21ae778ec5)

6) Run_placement
![run_placement](https://github.com/user-attachments/assets/d489e725-24d0-4a20-9004-3df4b07d8e27)
![run_placement_complete](https://github.com/user-attachments/assets/6a99138e-6762-4292-ba33-9fd9ec003943)


 7) load placement def in magic in other terminal
 
![magic](https://github.com/user-attachments/assets/3178192e-fe35-4ebb-8f9d-0b8fccb98432)

![vsdinv](https://github.com/user-attachments/assets/fcc38ff7-9a09-422c-82f2-38e9eb81becf)


8) tkcon window to view internal layers of cells

![expand](https://github.com/user-attachments/assets/2b868a31-917a-4845-8b1b-0bf315050a50)



9) New created pre_sta.conf for STA analysis in openlane directory

![pre_sta,conf](https://github.com/user-attachments/assets/65b23ef4-2caf-4d34-94ae-db122328daea)

10) my_base.sdc for STA analysis in openlane/designs/picorv32a/src

![my_sdc](https://github.com/user-attachments/assets/836ce71a-0d5d-4b46-9c7f-1ad763a83963)

11) output of pre_sta.conf is equal to synthesis stage

![openlaneoutput_negativeslace](https://github.com/user-attachments/assets/a0542931-4f42-44de-ac2a-9be371af96f0)

12) Here vsdinverter gate  is driving 4 fanouts

![or_gate_drive_strength_2_fanout_4](https://github.com/user-attachments/assets/ece2b905-229f-401a-9aa8-3002a3c075b8)

13) command to optimize 
```blash
	1. report_net -connections _10566_
	2. replace_cell _10566_ sky130_fd_sc_hd__or3_4
 	3. report_checks -fields {net cap slew input_pins} -digits 4
```

14) Befor optimizing

![newslackviolated_23 90](https://github.com/user-attachments/assets/e101f3ee-5860-458d-ad39-a5e65dc7828a)


15) After optimizing slack reduced
![newslack_afteroptimizing](https://github.com/user-attachments/assets/fecfb920-a039-418e-a4dc-6028c88dbee3)

16) or gate
![new_orgate_4fanout_before_optimize](https://github.com/user-attachments/assets/90ea3c92-022f-4ee1-89ce-ea5d98b00015)



6. #### Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
	
 	1. report_net -connections _11675_
	2.replace_cell _14514_ sky130_fd_sc_hd__or3_4
	3.report_checks -fields {net cap slew input_pins} -digits 4
1) before total slack
![befor_11675_total slack](https://github.com/user-attachments/assets/5d2ad9c8-a017-4c5c-a515-dd4bbe8049ef)

2) after optimizaiton 
![new_11675_delayreduced](https://github.com/user-attachments/assets/ec5f7127-ca64-4b40-aecb-6e10cbf5053f)

3) or gate _11675_
before
![new_11675_before](https://github.com/user-attachments/assets/7ab9f400-3e64-4f64-abaa-0b39680c35ca)
after
![new_11675_delayreduced](https://github.com/user-attachments/assets/84ecb9d5-3632-4271-9764-3bfe95ba152b)

#### We started ECO fixes at wns -23.90 and now we stand at wns 23.1405we reduced around 0.7595ns of violation



7. #### Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement and cts.

![oldnetlist](https://github.com/user-attachments/assets/c9e9ede3-28fe-44e1-86e3-98a59c45bf0f)

1) Commands to write verilog
	```blash
 	1.help write_verilog
  	2.write_verilog /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/09-09_05-51/results/synthesis/picorv32a.synthesis.v
	3. exit
        ``` 
 Screenshot of commands run
 ![write_Verilog](https://github.com/user-attachments/assets/9f9c2873-c84e-48b5-a46b-0249bb7f248c)

 2) Verified that the netlist is overwritten by checking that instance _14675_
![11675](https://github.com/user-attachments/assets/5a21f734-4cbe-4e59-9ba4-9558e56cb041)


3) we confirmed that netlist is replaced and will be loaded in PnR  , since we want to go with  0 violation design we will continuing with the clean design .
![slackzero](https://github.com/user-attachments/assets/2175ef0a-6405-4fbf-809d-fc2205f46840)

4) placement done 
![placementdone](https://github.com/user-attachments/assets/7690a971-24fd-4e06-86c9-ef97e8d4e4e3)

5) running _ cts
![run_Cts](https://github.com/user-attachments/assets/2f7731cf-a91c-43a0-8166-80d1e61327e9)

6) generated cts file in "/home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/09-09_05-51/results/synthesis" 
![cts_generated](https://github.com/user-attachments/assets/23e30600-812b-40b2-b452-30db6ca739da)


## 3] POST_CTS

1) commands performed 
	
 	1. openroad
![1_openroad](https://github.com/user-attachments/assets/f76680b5-dfda-406f-914f-d47d732d1066)

  	2. read_lef /openLANE_flow/designs/picorv32a/runs/09-09_05-51/tmp/merged.lef
![2_read_lef ](https://github.com/user-attachments/assets/5ce81d93-ae1d-4a2b-87ba-9a2848bf4906)

    	3. read_def /openLANE_flow/designs/picorv32a/runs/09-09_05-51/results/cts/picorv32a.cts.def
![4_read_def](https://github.com/user-attachments/assets/22f78503-0bfd-4425-ad03-75017b1089e3)

 	4. write_db pico_cts.db
![6_write_db pico_cts db](https://github.com/user-attachments/assets/7053030f-7d16-4d43-a570-a8d67799b441)
  
	5. read_db pico_cts.db
![8_read_db pico_cts db](https://github.com/user-attachments/assets/98607303-3960-4ece-9089-6382a638d93e)
	
 	6. read_verilog /openLANE_flow/designs/picorv32a/runs/09-09_05-51/results/synthesis/picorv32a.synthesis_cts.v
![9_read_verilog](https://github.com/user-attachments/assets/90553625-3604-452e-afcc-1c620de7c0e2)
  
  	7. read_liberty $::env(LIB_SYNTH_COMPLETE) 
![read_liberty $::env(LIB_SYNTH_COMPLETE)](https://github.com/user-attachments/assets/226a94b1-b0c2-4af1-8487-54c8f0ed992b)

    	8. link_design picorv32a
![10_link_design picorv32a](https://github.com/user-attachments/assets/d9c63f0b-1b72-42d8-9ef5-9f62615a045f)

    	9. read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc
![11_read_sdc ](https://github.com/user-attachments/assets/f00bb0c1-5d86-492e-8525-3ac3d179328b)

	10. set_propagated_clock [all_clocks]
![12_set_propagated_clock](https://github.com/user-attachments/assets/c3474d38-40da-4614-a861-74e1dfe963f5)

	11. report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4
![13_report_checks_output](https://github.com/user-attachments/assets/fa5e5e2c-f55c-4b97-bff0-31b56757779c)

 	exit

## 4] removing 'sky130_fd_sc_hd__clkbuf_1' cell from clock buffer list variable 'CTS_CLK_BUFFER_LIST'

1. command for removing    
     	1. echo $::env(CTS_CLK_BUFFER_LIST)
      	2. set ::env(CTS_CLK_BUFFER_LIST)  lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0
	3. echo $::env(CTS_CLK_BUFFER_LIST)
        
 ![14_removed_clk_buf1](https://github.com/user-attachments/assets/6feed76b-c69e-40c2-9ee9-bb3f8b7b6eba)

 2. Before running cts :
        
 	1. echo $::env(CURRENT_DEF)
	2. set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/09-09_05-51/results/placement/picorv32a.placement.def
        
        
![run_cts_before_placement_Cts](https://github.com/user-attachments/assets/00ed93b6-35d3-47d7-ba49-8668a24b4f98)
![running_cts_afterplacement_def](https://github.com/user-attachments/assets/971ffd45-6d7d-484f-8136-c7df6581f039)

3. completed running cts 
![completed run_cts_2ndtime](https://github.com/user-attachments/assets/cc108d71-e2b5-4be1-bef4-b4c2fe145fe8)
![read_def_2ndtime](https://github.com/user-attachments/assets/338fbfdf-2755-436d-8312-bbb96ef3acd5)

![Screenshot from 2024-09-13 16-15-31](https://github.com/user-attachments/assets/70a58477-4c32-421a-ade2-040ad9e93e40)
![hold](https://github.com/user-attachments/assets/72ce163f-952e-445d-abae-c174c37cd7d7)

![slack timing](https://github.com/user-attachments/assets/58f6f87a-91ce-4fc9-8a31-fed9a0261f40)

![alldone](https://github.com/user-attachments/assets/df046b6e-4aea-444c-87b5-b8fd27e5c9a7)

---
# #LAB-5
---

## 1] Lab steps to build power distribution network
```blash
 	1. Go to openlane directory : cd Desktop/work/tools/openlane_working_dir/openlane
	2. Type : Docker
 	3. Invode openlane : ./flow.tcl -interactive
  	4. package require openlane 0.9
	5. prep -design picorv32a -tag 09-09_05-51 
 	6. echo $::env(CURRENT_DEF)
```
  
![1](https://github.com/user-attachments/assets/f51883d8-c04e-4e94-976d-6583d9012301)

	7. gen_pdn
 	
![gen_pdn](https://github.com/user-attachments/assets/b0901c20-a811-4993-9eae-24180c6a1399)

![gen_success](https://github.com/user-attachments/assets/2ec5693f-49cd-4701-9129-f0c544c8fbcb)


![pdf def](https://github.com/user-attachments/assets/8916cee8-11e2-446d-b5da-ab998b22985d)

## 2] Def file generated :
![deffilegeneratded](https://github.com/user-attachments/assets/51004449-0291-4d52-a8ce-8b658c293ce6)
## 3] pdn def in magic file:

![magic](https://github.com/user-attachments/assets/6031f0c0-78ee-4838-91ee-a629fdcb1b69)

## 4] Run routing using - command - "run_routing"	
 
![runrouting](https://github.com/user-attachments/assets/14b53fed-a947-4a22-9a9f-712f338ec7e1)

![rouutinggg1](https://github.com/user-attachments/assets/30f07431-1808-4bd6-8d36-4cbf6bec4f4d)

![rouutinggg1](https://github.com/user-attachments/assets/bf173ce5-b4a2-470b-a8d1-170b323e82bf)


## 5] Fast route guide file 

![guide](https://github.com/user-attachments/assets/6fac3c73-7aa9-4657-97bf-853214264d34)

## 6] Completion of routing done.

![fjinish](https://github.com/user-attachments/assets/6e02497f-a5eb-4279-8af4-0a856a3cf617)

## 7] Violations is Zero

![Screenshot from 2024-09-14 21-58-19](https://github.com/user-attachments/assets/1dfa25cf-8187-4b88-a5f6-e2434498fc44)
---


