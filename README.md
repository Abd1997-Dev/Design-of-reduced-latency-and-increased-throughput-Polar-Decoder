# Design-of-reduced-latency-and-increased-throughput-Polar-Decoder
<p align="justify"> &emsp; The projects consists of the design and testbench files of polar decoder. The design is based on the research paper published on Signal Processing for communications Symposium 2012. The research paper name is "Reduced-Latency SC Polar Decoder Architecture" written by chuan zhang, Bo Yuan, and keshab K. parhi. </p>

**POLAR DECODER IMPLEMEMENTATION:**
<p align="justify"> &emsp; The algorithm for this polar decoder is similar to the butterfly diagram of the FFT (fast fourier transforms). The same is shwon in the fig. 1.
  
<p align="center">
<img src="https://user-images.githubusercontent.com/73669849/232680548-e9e87ef6-5de2-49c7-a1f3-577ccee59743.png" width="400" height="300">
</p>
<p align = "center">
Fig.1 - decoding process of polar codes with length N = 8
</p>

It is clear from the above diagram that there are two processing elements pe1(white) and pe2(grey). The basic building block and hardware architecture of the pe1 are shown in fig.2 and fig. 3 respectively. It consists of only full adder & subtractor and half adder & subtractor.

<p align="center">
<img src="https://user-images.githubusercontent.com/73669849/232682120-82e57154-9f15-44a4-a9bb-9be54c17010f.png" width="300" height="300">
</p>
<p align = "center">
Fig.2 - Basic Building Block of the pe1
</p>

<p align="center">
<img src="https://user-images.githubusercontent.com/73669849/232682643-e8ff888b-3ac0-4137-a479-0b7397751c93.png" width="600" height="300">
</p>
<p align = "center">
Fig.3 - Hardware architecture of the pe1
</p>

The corresponding schematic obtained from the xilinx vivado is attached in the fig. 4. I have used **structural modelling** to achieve the required architecture. [**Note: The block diagram in the paper takes the inputs from right side and gives the ouputs through left side. but in the schematic it is reversed. Applicable for all the following figures**]

<p align="center">
<img src="https://user-images.githubusercontent.com/73669849/232690066-a691e641-3c87-41f4-8f15-7cf19d5b487e.png" width="600" height="300">
</p>
<p align = "center">
Fig.4 - Schematic of the pe1 using Xilinx Vivado
</p>


The pe2 uses the min-sum approach and its hardware architecture is shown in fig. 5. It consists of the two complement to sign magnitude conversion, sign magnitude to two cmplement conversion, EX-OR gate and comparator.

<p align="center">
<img src="https://user-images.githubusercontent.com/73669849/232683862-0e1d7828-f2c5-4fcf-82b4-aa6bd37c9528.png" width="600" height="300">
</p>
<p align = "center">
Fig.5 - Hardware architecture of the pe2
</p>

The corresponding schematic obtained from the xilinx vivado is attached in the fig. 6.

<p align="center">
<img src="https://user-images.githubusercontent.com/73669849/232690592-4b568e88-216d-477d-855f-e3dd0d16b461.png" width="600" height="300">
</p>
<p align = "center">
Fig.6 - Schematic of the pe2 using Xilinx Vivado
</p>


The comparator in the pe2 can be replaced with the subtractor in the pe1 and that approach is known as **sub-structure sharing** approach and it is used to obtain the merged pe2 element in this research paper. The merged pe2 hardware architectrue is shown in fig. 7.

<p align="center">
<img src="https://user-images.githubusercontent.com/73669849/232685196-399ab8bf-2f94-44c6-a8f6-0114ab7a1f52.png" width="600" height="300">
</p>
<p align = "center">
Fig.7 - Hardware architecture of the merged pe1 and pe2
</p>

The corresponding schematic obtained from the xilinx vivado is attached in the fig. 8.

<p align="center">
<img src="https://user-images.githubusercontent.com/73669849/232694056-fd29fe81-3bef-42b5-bc25-946130f43a96.png" width="600" height="300">
</p>
<p align = "center">
Fig.8 - Schematic of the merged pe1 and pe2 using Xilinx Vivado
</p>



**Conclusion:**

The Implementation of all the above modules are completed in the verilog HDL using the xilinx Vivado 2020.2. The verilog code and the schematic are attached with this repository.

**Future works:**

To implement the complete polar decoder using pipelined architecture as shown in the research paper.

**Reference:**

[1] Chuan Zhang, Bo Yuan, and Kesahb K. Parhi,"Reduced-latency SC Polar decoder Architectures" in IEEE ICC 2012 - Signal Processing for Communications Symposium.

**Behind the scene approach to finalise this paper for the design:** 
<p align="justify"> &emsp; The various research paper from top conferences and journals based on the polar decoder is referred and the basic understanding of the polar decoder is obtained. Then, the hardware architecture of the polar decoder is obtained from one paper [mentioned above] to implement using the verilog HDL. </p>


