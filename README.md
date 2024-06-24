# 6T-SRAM

* SRAM has become a major component in many VLSI Chips due to their large storage density and small access time. SRAM has become the topic of substantial research due to the rapid development of low-power, low-voltage memory design during recent years due to increased demand for notebooks, laptops, IC memory cards, and handheld communication devices.
* 6T static random-access memory is a type of semiconductor memory that uses bistable latching circuitry to store each bit. The term static differentiates it from dynamic RAM which must be periodically refreshed. SRAM exhibits data remembrance but is still volatile in the conventional sense, that data is eventually lost when memory is not powered. 

![Basic cell sch](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/9d2b4ef9-69f5-4588-8458-9266d5e2b25e)

The two basic requirements of an SRAM cell can be understood as follows:
1. Read Stability: The data once read from an SRAM cell should remain stable and not be upset or altered by the read operation itself. *Read upset* refers to the unintentional alteration of data due to the process of reading. To avoid Read upset the Cell ratio β should be greater than 1 <br> 
``` Cell ratio, β ={ (W\L) pull-down transistors } / {(W\L) access transistor} ```
2. Write Stability: When data needs to be written to an SRAM cell, the cell should reliably accept the new data and update its stored value without causing read upset or other unintended changes to neighboring cells or circuitry. This ensures that the SRAM cell maintains its stability and integrity during write operations, allowing for accurate storage and retrieval of data. This is ensured by maintaining the Pull up ratio, given by <br>
```Pull-up ratio, P.R ={ (W\L) pull up transistors } / {(W\L) access transistor } ```

#### Read operation
* To read data from the cell, the wordline (WL) connected to the access transistors is activated allowing access to the storage nodes.
* If the cell is storing a logic high (1), the bitline (BL) connected to the output of the latch will be discharged to a logic low (0) due to the pull-down action of the cross-coupled NMOS transistors.
* If the cell is storing a logic low (0), the bitline will remain at logic high (1) due to the pull-up action of the cross-coupled PMOS transistors.

#### Write operation
* To write data into the cell, the bitline (BL) and wordline (WL) are appropriately controlled.
* For writing a logic high (1) into the cell, the BL is precharged to logic high (VDD) and the WL is brought to logic high (VDD) to enable the access transistors. This causes the cell to latch a logic high due to the feedback provided by the cross-coupled inverters.
* For writing a logic low (0) into the cell, the BL is discharged to logic low (0) and the WL is brought to logic high (VDD).

*With CR=1.25 and PR=0.85 using 180nm and width of pull up transistors(wp) fixed at 400nm we get*
1. Width of access transistors Wa= 470nm
2. Width of pulldown transistors Wn= 590nm

![Basic_sch](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/01621261-6dfd-49c1-9221-1fc4269c1bce)

#### WRITE '0' Operation
* The write driver makes BL=0V and BL'= VDD
* Word line WL is made high

![write0_ckt](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/a6c58e8b-72f9-4c07-bde5-8ac479225477)
![write0_grf](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/aaa72073-6061-41a7-b831-a5bb2b83a9f8)


#### WRITE '1' Operation
* The write driver makes BL=VDD and BL'= 0
* Word line WL is made high

![write1_ckt](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/46a0f26c-382e-481d-b2d7-5e41a19bd928)

![write1_grf](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/80005edc-2593-4396-9180-d6f2a7dd4c80)


#### READ '0' Operation

![read0_grf](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/c8cab5ba-3082-4b16-a55e-493be6cd4e38)
![read0_ckt](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/07357d78-097c-45e5-be77-4d301216795c)

#### READ '1' Operation
![read1_ckt](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/fe7f3e6f-f7d8-4ab6-a0fc-8faa0d53ac3e)
![read1_grf](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/5c75d2bb-8ad5-4209-8ee7-377014368cf3)

#### Precharge circuit
* In Static Random Access Memory (SRAM), precharge circuits play a crucial role in preparing the bit lines before a read or write operation.
* Precharge circuits ensure that the bit lines are at a known voltage (typically 𝑉𝐷𝐷) before a read or write operation. This helps in accurately sensing the small voltage difference during read operations.
* Precharging the bit lines reduces power consumption and noise by minimizing the voltage swings during operations.

![Precharge_ckt](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/2195ded5-23df-4834-bdfc-72a7cb6c8ea0)
![Precharge_grf](https://github.com/Karthik-6362/6T-SRAM/assets/137412032/e49b5fc8-dac4-4a68-84b9-bab621dfd8a1)


