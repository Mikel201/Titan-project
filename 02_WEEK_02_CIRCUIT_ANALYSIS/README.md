READ.ME 
 
OBJECTIVE; 
The objective of this project was to design and simulate a circuit component in series and also in parallel, using Ltspice in order to understand the relationship between voltage, current and the resistance of different component when connected together in series, parallel or series-parallel. 
 
                CIRCUIT COMPONENT 
1.	Dc voltage source 
2.	Wires 
3.	Resistors 
 
 
THEORETICAL CALCULATION  
   SERIES COMPONENT/CONNECTION; 
This circuit have all component connected by a single wire with the same current flowing through every component; voltage is divided among the component. 
Resistors in series; 
Rt= R1+R2+R3....+Rn 
I, current remain the same although while voltage changes 
Voltage can be calculated  using ohms law; Vt=It*Rt 
Individual voltage can be calculated using 
V1=It*R1 
V2=It*R2...... 

      PARALLEL CONNECTION; 
In a parallel circuit, the voltage across each branch is the same, while the total current divides among the branches.
1/Rt=1/R1 +1/R2 + 1/R3..... + 1/Rn 
Vt remain the same although the component 
We can find current using ohms law; Vt=It *Rt 
It=I1+I2+I3....+In 

     SERIES-PARALLEL CIRCUIT 
This is a combination of both the series circuit and the parallel circuit. it contain portions of the circuit connected in series and other portions connected in parallel. 
   
    KIRCHHOFF'S CURRENT LAW(KCL) 
The total current entering a node equals to sum of the individual current leaving the node. sum of Iin= sum of Iout 
Iin =Iout 
Where Iin is the total current entering into the node Iout is the total current leaving the node 
     
     KIRCHHOFF'S VOLTAGE LAW (KVL) 
State that the algebraic sum of all the voltage changes around a  closed loop is zero 
Vin-vout=0      vin is the total voltage entering the loop while Vout is the total voltage leaving the loop 
                  
                 THEORY VS SIMULATION 
From the calculation using ohms law, you can calculate the voltage drop across each resistors when the component is connected in series while the current will current remain constant although the series connection. In a parallel circuit, the voltage across each branch is the same, while the total current divides among the branches, current changes as it from through the component in parallel connection. 
 
Simulation; from simulation it can be seen the there is actually a voltage drop across each resistors when they are connected in series, same current flows through the circuit.  While voltage remain the same when applied across resistors in parallel but the current changes as it moves through the circuit. 

    SIMULATION RESULT

   Series Circuit

image available on draft3.s page

Calculated:
- Total resistance = 12 Ω
- Total current = 1 A
- Voltage across R1 = 2 V
- Voltage across R2 = 4v V
- Voltage across R3 = 6v

LTspice:
- Measured current = 1 A
- Measured voltage across R1 = 2 V
- Measured voltage across R2 = 4 V
- Measured voltage across R3 = 6v

 Parallel Circuit

[schematic available on Draft3.s]

Calculated:
- Equivalent resistance = 3 Ω
- Branch current 1 = 2 A
- Branch current 2 = 2 A
- Total current = 4 A

LTspice:
- Branch current 1 = 2 A
- Branch current 2 = 2 A
- Total current = 4 A
 
                                WHAT I HAVE LEARNED  
From the simulation, i learned that: 
1.	Current remain the same at any point in a series connection 
2.	Current varies across each path in a parallel circuit 
3.	Voltage drop across each resistors in goes through in a series circuit 
4.	Voltage remain the same across each path in a parallel circuit 
5.	In a close loop, the amount of voltage entering is equivalent to the amount of voltage leaving the loop. Vin -Vout =0 
6.	The sum of all the current entering a node is equal to the current exiting the node 
     
        ENGINEERING APPLICATION   
Some of the engineering application include 
1.	Conservation of energy; energy supplies is equal to the energy being used 
2.	Conservation of charge; what goes in must come out 
3.	Resistors connected in parallel would have a lesser resultant Resistance then the one connected in series  
 
