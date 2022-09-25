# CMOS-NOR-Gate-Design-using-Cadence-Virtuoso
### 2-input CMOS NOR Gate Design and Analysis with Layout using Cadence Virtuoso

---
<!-- Cadence Project (Transient, DC, AC & Noise Response With Layout) -->

I’m really glad to share that, this is my third project on __Cadence Virtuoso__. I am designing here a 2-input CMOS NOR Gate with its layout.

___Before I start explaining my project in details, you should know a few things !___     

### What is CMOS NOR Gate?  
The NOR gate is a digital logic gate that implements logical NOR - it behaves according to the truth table to the right. A HIGH output (1) results if both the inputs to the gate are LOW (0); if one or both input is HIGH (1), a LOW output (0) results. NOR is the result of the negation of the OR operator. It can also in some senses be seen as the inverse of an AND gate. NOR is a functionally complete operation—NOR gates can be combined to generate any other logical function. It shares this property with the NAND gate. By contrast, the OR operator is monotonic as it can only change LOW to HIGH but not vice versa.

In most, but not all, circuit implementations, the negation comes for free—including CMOS and TTL. In such logic families, OR is the more complicated operation; it may use a NOR followed by a NOT. A significant exception is some forms of the domino logic family.

### The Project details of mine :
Here i have use __gpdk90n__ :-
1. Two pmos1v and Two nmos1v. The pmos are is in series and the nmos is in parallel.
2. For vdd i have use vdc (1.8v)
3. For input i have use two vpulse (1.8v)
4. Here I am doing four types of Analysis :  
    i ) Transient Response  
    ii ) DC Response  
    iii ) AC Response  
    iv ) Noise Response & Noise Figure  
    N.B. I'm measuring here 2 inputs & output as Voltage and Current (I) in Vout & VDD node.
5. In Layout - Metals Used ( Metal1 ) and Poly Layer
6. The minimum width of metal utilized for routing is 0.12
7. DRC and LVS clean (there are no error)

So I designed a Schematic of the CMOS NOR Gate, where the whole thing is based on gpdk90n. I have use 2 pmos for 1v and 2 nmos for 1v. I also designed a symbol of it, so that i can utilise that for further schematic creation.  

The below figure shows a 2-input CMOS NOR Gate. It consists of two PMOS connected in series and two NMOS connected in parallel.

Step-1 : Va = Low & Vb = Low

Va = Low: PM0 – ON; NM0 – OFF  
Vb = Low: PM1 – ON; NM1 – OFF

Path establishes from Vdd to Vout through the series connected ON PMOS transistors and Vout gets charged to Vdd level. No path from Vout to GND. Therefore, no discharging and hence Vout will be High.

Step-2 : Va = Low & Vb = High

Va = Low: PM0 – ON; NM0 – OFF  
Vb = High: PM1 – OFF; NM1 – ON

In this case path establishes from Vout to GND through NM1, but no path to Vdd. So, Vout would get discharged and will be at level Low.

Step-3 : Va = High & Vb = Low

Va = High: PM0 – OFF; NM0 – ON  
Vb = Low: PM1 – ON; NM1 – OFF

The explanation is similar as step-2. Vout will be at level Low.

Step-4 : Va = High & Vb = High

Va = High: PM0 – OFF; NM0 – ON  
Vb = High: PM1 – OFF; NM1 – ON

No path to Vdd. Path establishes from Vout to GND. So, Vout will be at level Low.

Considering all 4 steps will show that Vout is following the expected value as in 2 input NOR gate truth table.

![Scametic](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Scametic.PNG?raw=true) 
![Symbol](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Symbol.PNG?raw=true)
![Symbol_Scametic](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Symbol_Scametic.PNG?raw=true)

#### DC, AC, Transient and Noise Response :
_Here I am doing four types of Analysis - DC, AC, Transient and Noise_.  
In DC and Transient Analysis i have measured Va, Vb & Vout as Voltage, and Current (I) in Vout & VDD node. In AC Analysis i have measured Va, Vb & Vout as Voltage Frequency and Current (I) Frequency in Vout & VDD node. For Noise Analysis i have measured input & output noise. For DC and Transient Analysis the plots of _Va_ , _Vb_ and _Vout_ shows the _voltages_, on the otherhand _VDD(I4)_ & _Vout(I4)_ shows the _current (I)_. For AC Analysis the plots of _Va_ , _Vb_ and _Vout_ shows the _voltage frequency_, on the otherhand _VDD(I4)_ & _Vout(I4)_ shows the _current (I) frequency_. In Noise Response the plots shows the input and output noise.
![output](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Output.PNG?raw=true)
![output2](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Output_2.PNG?raw=true)
![AC_output](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/AC_Output.PNG?raw=true)
![noise_output](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Noise%20Analysis%20(IN,%20OUT).PNG?raw=true)  

#### Noise Figure :  
For measuring of Noise Figure i had to use PORTS instead of Vpulse.  
![noise_figure_scametic](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/NF_scametic.PNG?raw=true)
![noise_figure](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Noise%20Figure_Output.PNG?raw=true)

#### Layout :
In Layout i have use  Metal1 and Poly Layer. I have use here X & Y snap spacing is 0.01m and also the minimum width of metal utilized for routing is 0.12.  
![Layout](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Layout.PNG?raw=true)  

#### Design Rule Check (DRC)  
DRC is clean. There are no error in DRC.
![DRC](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/DRC%20Check.PNG?raw=true)  

#### Layout Versus Schematic (LVS)  
LVS is clean. There are no error in LVS.  
![LVS](https://github.com/wreasin/CMOS-NOR-Gate-Design-using-Cadence-Virtuoso/blob/main/image/LVS%20Check.jpg?raw=true)
