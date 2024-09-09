# Digital VLSI SoC Design and Planning

## LAB-1

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
6. #### Design Setup Stage
   > prep -design picorv32a

##### Screenshots of running each commands
![Screenshot 2024-09-09 093606](https://github.com/user-attachments/assets/d20f21df-a853-40dd-9890-0894e5694285)

7. #### Run Synthesis
   > run_synthesis

##### Screenshots of running each commands
![Screenshot 2024-09-09 094316](https://github.com/user-attachments/assets/bd3c4df3-b9ba-4378-9767-34db57e39596)







