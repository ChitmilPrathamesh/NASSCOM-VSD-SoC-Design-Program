# Digital VLSI SoC Design and Planning

## LAB-1

## 1] Run 'picorv32a' design synthesis using OpenLANE flow and generate necessary outputs.

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






