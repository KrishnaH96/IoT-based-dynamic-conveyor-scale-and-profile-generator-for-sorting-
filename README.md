# IoT-based-dynamic-conveyor-scale-and-profile-generator-for-sorting-

# 1. Introduction:
In line with today's advanced aircraft design and technology, it is necessary for logistics industry to adapt a new computation in order to make efficient use of cargo space and to avoid over-bulking. By doing this, industries can better streamline their operations and in the process, deliver the benefits of space saving back to their customers.
Hence, the logistics industry has shifted its approach from Conventional weighing to Volumetric weighing. Conventional weighing takes into account only the weight of the package irrespective of its dimensions.
The major limitations of conventional methods of weighing are:
1. No co-relation between weight and size of the package.
2. The losses incurred due to this approach are very large when considered for longer periods.

The volumetric weight of a shipment is a calculation that reflects the density of a package. A less dense item generally occupies more volume of space, in comparison to its actual weight. The volumetric or dimensional weight is calculated and compared with the actual weight of the shipment to ascertain which is greater; the higher weight is used to calculate the shipment cost.

![image](https://user-images.githubusercontent.com/113392023/234103583-6dfb8c4e-3419-4182-be15-f17cc698ab0f.png)

If the package dimensions and weight are measured manually it has the following limitations:
1. Manual measurement of package dimensions increases operation time
2. Increases possibility of human errors

Dynamic weighing ensures that all the packages are weighed as they move along the conveyor without stopping the conveyor giving it superiority over the traditional manual pickup and weighing approach.
The combination of Volumetric and dynamic weighing enables us to tackle the above-mentioned limitations and hence significantly reduce the operation time, human-induced errors and increase the overall reliability of the system.
Another problem faced by the logistics industry is to sort the packages according to the specified criteria. As an example, there may be a need to sort the packages according to their final destination. Also, if they have to be transported by air they must be sorted according to their weight and volume so that they can be correctly loaded onto the airplane. The need for a flexible sorting mechanism which can readily adapt to these changing parameters is the need of the hour. Automating the process of sorting in the industry helps us greatly reduce the operational time and increase the throughput of the system.

## CASE STUDY:

The transport costs for shipments are calculated on the basis of the total weight of all packages sent under one FedEx Air Waybill. A decisive factor for calculating the price, however, is whether the dimensional weight exceeds the actual weight.

FedEx applies: Since 18 January 2010, shipments where dimensional weight exceeds actual weight are charged according to the following volumetric calculation:

```
Dimensional weight in kg per package = Length x Height x Width in cm / 5,000.
```

This dimensional weight calculation for FedEx Express services applies to Europe, Middle-East, Africa and the Indian Subcontinent (EMEA), EMEA export and EMEA import shipments.

# 2. Concept of the Proposed model:

Conveyor based dimension and weight measurement systems are capable of automating the process of manual weighing and dimensioning the packages. These systems are used to generate a profile of the package (dimensions and weight measurement) in motion. Further, a mechanism which can sort objects according to configurable parameters is desired. These parameters can be remotely controlled by the factory operator, thus connecting IoT based web applications to the upper layers of the Manufacturing Execution System (MES). This can enable us to increase the productivity of the operation several times and make the entire process transparent, reliable and repeatable.

We aim to develop a system to automate all these functionalities in 3 stages.

The first stage of the operation is package dimensioning followed by weight measurement and package sorting based on configurable parameters. The controlling and synchronization of the complete system is done through a PLC which is responsible for controlling the actuators according to input data from the sensors. The PLC accepts sensor data from measuring array which measures the package dimensions and the load cell which measures the weight of the package in motion. The PLC also controls the Servo System and Motors which are used to drive the conveyors. High positional and speed accuracy is desired during weight measurement of the package in motion. This is accomplished by accurately controlling the Servo System. The pneumatic piston actuators are activated by the PLC making a decision according to the sorting criteria.

## Conceptual representation of the system:

![image](https://user-images.githubusercontent.com/113392023/234104322-ee4facd8-0088-48bb-b27d-69a9410e5239.png)
  
  
## Functional Block Diagram

<img width="685" alt="image" src="https://user-images.githubusercontent.com/113392023/234104459-f2240b44-87b0-4e19-a5bc-5ebfe34c3014.png">


# 3. Detailed Working of the prototype:

The system comprises of three workig stations

## STATION 1: (FEEDING AND DIMENSIONING STATION)

The package is loaded on the conveyor of the first station where a pneumatic mechanism ensures straightening of the package. This package then passes through a vertically arranged measuring laser array.

The arrangement of measuring arrays is as shown in fig.

![image](https://user-images.githubusercontent.com/113392023/234104681-d73b88cc-a830-40a9-8e0f-27fe098a1efc.png)

The measuring arrays detect items as small as 5 mm wide and have high excess gain for detecting opaque objects. These features allow for reliable detection and width measurement of packages that pass through the measuring arrays.

The total number of beams blocked for each pair indicates the size, which is sent to Mitsubishi FA PLC as an analog signal. Number of beams of vertical array blocked will indicate width.

For calculating the height of the package, an ultrasonic sensor is used which is placed on the junction point of the first two conveyors.
The dimensional data collected from the measuring arrays and the ultrasonic sensor will be relayed to the PLC which will be further displayed on the Mitsubishi FA HMI.

Station 1 houses the system MCB which offers overcurrent protection and the Emergency Stop Switch for the system.

## STATION 2: (WEIGHING STATION)

This station is used to calculate the actual weight and length of the package. If the conveyor is stopped for weighing the package it would increase the operation time of the system. Weighing the package in motion is the most crucial part, it decreases the operation time, resulting in reduction of cost. We aim to tackle this problem with our solution. The conveyor used in this weighing section is isolated from the other two stations so that there is no transmission of forces and accuracy of weighing is ensured.

A proximity sensor mounted on this station is used for calculating the length of the package. The product of time for which the proximity sensor is blocked and the constant speed of conveyor will give the length of the package.

The mechanical assembly of the weighing station is as shown in the figure.

![image](https://user-images.githubusercontent.com/113392023/234104859-710e81eb-44e0-45ef-a587-5f0373bfc333.png)

The mechanical assembly of the weighing conveyor is supported on Shear beam load cells which are ideal solutions for multiple load cell weighing applications typical of belts and roller conveyor scales. The load cells are positioned in such a way that uniform distribution of the load is ensured.

The speed of the weighing station conveyor is controlled by VFD.

## STATION 3: (SORTING STATION)

The aim of this station is to sort the packages on the basis of parameters which can be altered by the factory operator using e-factory concepts.
The mechanical arrangement of sorting station is as shown in the figure.

![image](https://user-images.githubusercontent.com/113392023/234104939-2e218cc7-cfcf-44b5-9052-84b642326fe4.png)

The double acting solenoid operated pneumatic cylinders which are controlled by Mitsubishi FA PLC are used for sorting of the packages. Sorted Packages are collected in bins.

These piston actuators can be configured to sort the packages according to any of the following requirements:
a. Differentiating error checked packages
b. Weight of the packages
c. Volume of the packages

All these applications can help reduce the cost, labor and time of the carrier company.

# 4. Actual Model Photographs:

![image](https://user-images.githubusercontent.com/113392023/234105018-cb1a2527-bc0b-40f8-9b8a-666c9375c983.png)

![image](https://user-images.githubusercontent.com/113392023/234105082-a0792a84-3bba-4d3d-8d48-3f64b31e5af8.png)


# 5. Electrical and Mechanical Section:

## FBD for Load Cell calibration:

![image](https://user-images.githubusercontent.com/113392023/234105160-b420c355-e52f-43ed-8f15-17e19a20b9a4.png)


## FBD for Ultrasonic Sensor Calibration:

![image](https://user-images.githubusercontent.com/113392023/234105215-23d59179-1dd6-49e7-89a5-df8a38eca179.png)

## Conditioning Circuit:

![image](https://user-images.githubusercontent.com/113392023/234105252-621a47fe-4f38-48e0-aed3-b28945d7816c.png)

## Detailed Drawing of the Assembly:

The upper conveyor assembly as shown in the drawing below is same for all the three stations. Base support assembly is used in the second weighing station.

![image](https://user-images.githubusercontent.com/113392023/234105326-985c2eef-657a-43ba-9f59-47c0d60079b1.png)

## PLC Ladder Logic:

![image](https://user-images.githubusercontent.com/113392023/234105380-005c3bfa-f4c3-4c89-9c16-a8b7897fe917.png)
![image](https://user-images.githubusercontent.com/113392023/234105396-63a384a5-fc49-42f4-90fa-ad4904a72ddf.png)
![image](https://user-images.githubusercontent.com/113392023/234105415-8ef89c11-04f8-4abc-bcae-91cce846bfaa.png)

## Other Electronics parts:

1. The ultrasonic sensor needs a very accurate timer which has a resolution in micro seconds for getting accurate measurement of distance. The PLC cannot provide timers with accuracy in micro seconds.
Solution:
We are using Arduino which can generate the required timer value.
2. Need of DAC :
Solution:
The Arduino doesn’t have an inbuilt DAC so as to produce analog output which can be given as input to ADC of PLC. Therefore, we use an external DAC followed by an amplifier circuit to get the required analog voltage in 0-10 V range.

# 6. Functioning of FA Components

## PLC:
PLC is a Main control unit, all sensory inputs are connected to PLC including Laser Array, ultrasonic sensor, strain gauges and proximity sensors. Proximity sensors locate the package on the conveyor, using which PLC triggers the data collection through different sensors. PLC uses socket communication for data exchange.


## Servo and Servo Amplifier:
Servo is used as a driving motor for the first conveyor which will allow it to operate intermittently in order to ensure that only one package is weighted at a time on the second moving conveyor.

## VFD:
Apart from the first conveyor, the second and the third ones are operating continuously which have high energy requirement. The use of induction motors via VFD will help in energy savings over the longer period.

## HMI:

For displaying the current status of the process as well as for keeping a track of the information of the previous packages, an HMI proves to be the perfect ergonomic interface between the system and the operator.

## MCB:
Two MCB’s are used in the entire system. 10 ampere MCB for switching off the complete system and the 6 amp MCB for switching off the servo system.

# 7. E&Eco Factory concepts:

At the Sorting Station, the PLC must be tuned to certain parameters. It is according to these parameters that the piston based actuators are activated and sorting is done. The ability of the factory operator to control these parameters remotely increases the productivity of the operations several times. The same approach can also be applied for the benefit of the customer. For example, the customer will be able to monitor the status of his parcel in real time when the factory is connected to the internet. The status of the product will be updated at every station. This will increase the transparency and reliability of the operations.

The use of Inverters (VFD) to control the conveyor speed at Station 2 & 3 not only eliminates Wastefulness and surges in energy consumption but also reduces overall power usage. As an example when the factory doesn’t need to operate at its full capacity the operations can be scaled down to conserve energy and can be restored to normal when needed.

# 8. Justification to the theme: ‘Innovative Solutions for Smart Manufacturing’:

- Dynamic weighing – In-motion weighing results in reduced operation time, human-induced errors, and space requirements.
- Sorting of packages – Provision for varying the sorting parameters given by the user increases the proficiency of the system.
- Smarter process design – Dimensioning, weighing, and sorting in a single system.
- Design of dynamic weighing assembly.
- Remote monitoring and control of sorting parameters – By leveraging IoT technologies.

# 9. Achievements and Conclusions:

We have successfully built a system, which integrates state-of-art technologies to solve a complex problem related to logistics. We have successfully fabricated a dynamic conveyor scale for in motion weighing which gives weight readings with 10gm accuracy. We have achieved dimensional accuracy of 5mm by laser array. We are able to extract sensory data from PLC through Socket communication.

## Assumptions:

1. The parcel is straight when it is loaded on the conveyor.
2. The system to be accommodated in 1.5m cube, hence travel along three conveyors is limited.
3. Specifications of the packages:
  -Length: 8-30 cm
  -Width: 2-19 cm
  -Height: 2-23 cm
  -Weight: 10-2000 gm
  
## Future scope:

- Object Straightening mechanism
- Data can be used for error check using advanced IoT and web integration.


# 10. Fabrication of the model (Reference Images):

![WhatsApp Image 2023-04-22 at 2 49 14 AM (1)](https://user-images.githubusercontent.com/113392023/234107036-57bd9a41-94b1-4149-a444-60235b5013aa.jpeg)

![WhatsApp Image 2023-04-22 at 2 49 14 AM](https://user-images.githubusercontent.com/113392023/234107060-8e34a299-aa1f-42d5-8c80-26367fb484ff.jpeg)

![WhatsApp Image 2023-04-22 at 2 49 13 AM (2)](https://user-images.githubusercontent.com/113392023/234107076-37175ee4-d79f-4eef-adcb-b005232b9185.jpeg)

![WhatsApp Image 2023-04-22 at 2 49 13 AM](https://user-images.githubusercontent.com/113392023/234107094-c3d78b1d-e9af-425e-ac51-80cecf748cdb.jpeg)

![WhatsApp Image 2023-04-22 at 2 49 13 AM](https://user-images.githubusercontent.com/113392023/234106651-97835bda-7816-434e-974e-efae17463351.jpeg)

![WhatsApp Image 2023-04-22 at 2 49 14 AM (2)](https://user-images.githubusercontent.com/113392023/234106621-f094c57e-a212-440a-b9c1-bc9f17d20304.jpeg)
