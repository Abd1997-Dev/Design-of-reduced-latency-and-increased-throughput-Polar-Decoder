# Design-of-reduced-latency-and-increased-throughput-Polar-Decoder
<p align="justify"> &emsp; The projects consists of the design and testbench files of polar decoder. The design is based on the research paper published on Signal Processing for communications Symposium 2012. The research paper name is "Reduced-Latency SC Polar Decoder Architecture" written by chuan zhang, Bo Yuan, and keshab K. parhi. </p>

**Behind the scene approach to finalise this paper for the design:** 
<p align="justify"> &emsp; The various research paper from top conferences and journals based on the polar decoder is referred and the basic understanding of the polar decoder is obtained. Then, the hardware architecture of the polar decoder is obtained from one paper [mentioned above] to implement using the verilog HDL. </p>

**POLAR DECODER IMPLEMEMENTATION**
<p align="justify"> &emsp; The algorithm for this polar decoder is similar like the butterfly diagram of the FFT (fast fourier transforms). The same isshwon in the fig. 1.
  
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
<img src="https://user-images.githubusercontent.com/73669849/232682643-e8ff888b-3ac0-4137-a479-0b7397751c93.png" width="300" height="300">
</p>
<p align = "center">
Fig.3 - Hardware architecture of the pe1
</p>





