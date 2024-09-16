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

5. #### Calculate Rise Time:
  ##### Subtract the time at 10% from the time at 90% to get the rise time.

            Rise Time = T80%−T20%
            80 % of 3.3V is 2.64 
            20 % of 3.3V is 0.66
---

![80%2 64command](https://github.com/user-attachments/assets/a2798e96-b320-4ff2-ac22-890aebf1efe9)
. 80 Percent of 3.3V is 2.64
![80%2 64](https://github.com/user-attachments/assets/ae4da3fb-4428-48bd-ac9b-dd2e25cd4f9a)
. 20 Percent of 3.3V is 0.660
![20%660](https://github.com/user-attachments/assets/aabe8117-a89c-4bce-8c81-1c50cb7280b1)
. Rise Transition time = 6.16096 - 4.03964  = 2.12132ps
