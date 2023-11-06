# ferroamp Binding

The ferroamp binding is used to get live data from ferroamp energy systems.

The binding retrieve data from the different parts of the ferroamp energy system such as:

- `Ehub`: EnergyHub Wall and EnergyHub XL.
- `Sso`: Solar string optimizer.
- `Eso`: Bidirectional DC/DC converter for connection of battery.
- `Esm`: Energy Storage Module.
 

## Supported Things

This binding is compatible with EnergyHub Wall and EnergyHub XL, and use connection to your local Ehub via LAN or similar.
Data and commands are sent using MQTT where the user connects to the MQTT broker residing on the ferroamp system.
Contact ferroamp support to enable MQTT in the EnergyHub and to get Username and Password:
https://ferroamp.com/om-ferroamp/

## Discovery

Discovery is not supported, as the system has a number of fixed parameters.

## Thing Configuration

Binding MQTT must be installed before binding ferroamp.

Installing of binding ferroamp and configuration of it can be done in the UI.

The following configuration-parameters are available for the `ferroamp` binding.

| Name            | Type    | Description                           | Default | Required | Advanced |
|-----------------|---------|---------------------------------------|---------|----------|----------|
| hostname        | text    | Hostname or IP address of the device  | N/A     | yes      | no       |
| username        | text    | Username to access the device         | N/A     | yes      | no       |
| password        | text    | Password to access the device         | N/A     | yes      | no       |
| hasBattery      | boolean | Is there a battery connected or not ? | N/A     | no       | yes      |


## Channels

The following channels are available for the ferroamp binding.

| Channel Type ID                   | Item Type               | Read/Write | Description                              |
|-----------------------------------|------------------------ |------------|------------------------------------------|
| device-local-ehub-wloadconsq-l1   | Number:Energy           | R          |                                          |
| device-local-ehub-wloadconsq-l2   | Number:Energy           | R          |                                          |
| device-local-ehub-wloadconsq-l3   | Number:Energy           | R          |                                          |
| device-local-ehub-iloadd-l1       | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iloadd-l2       | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iloadd-l3       | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-winvconsq_3p    | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-wextconsq-l1    | Number:Energy           | R          |                                          |
| device-local-ehub-wextconsq-l2    | Number:Energy           | R          |                                          |
| device-local-ehub-wextconsq-l3    | Number:Energy           | R          |                                          |
| device-local-ehub-winvprodq_3p    | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-winvconsq-l1    | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-winvconsq-l2    | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-winvconsq-l3    | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iext-l1         | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iext-l2         | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iext-l3         | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iloadq-l1       | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iloadq-l2       | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iloadq-l3       | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-wloadprodq_3p   | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-iace-l1         | Number:ElectricCurrent  | R          | ACE equalization L1                      |
| device-local-ehub-iace-l2         | Number:ElectricCurrent  | R          | ACE equalization L2                      |
| device-local-ehub-iace-l3         | Number:ElectricCurrent  | R          | ACE equalization L3                      |
| device-local-ehub-pload-l1        | Number:Power            | R          |                                          |
| device-local-ehub-pload-l2        | Number:Power            | R          |                                          |
| device-local-ehub-pload-l3        | Number:Power            | R          |                                          |
| device-local-ehub-pinvreactive-l1 | Number:Power            | R          | Inverter power, Reactive L1              |
| device-local-ehub-pinvreactive-l2 | Number:Power            | R          | Inverter power, Reactive L2              |
| device-local-ehub-pinvreactive-l3 | Number:Power            | R          | Inverter power, Reactive L3              |
| device-local-ehub-ts              | String                  | R          | Time stamp when message was published    |
| device-local-ehub-ploadreactive-l1| Number:Power            | R          |                                          |
| device-local-ehub-ploadreactive-l2| Number:Power            | R          |                                          |
| device-local-ehub-ploadreactive-l3| Number:Power            | R          |                                          |
| device-local-ehub-state           | String                  | R          | State of the system                      |
| device-local-ehub-wloadprodq-l1   | Number:Energy           | R          |                                          |
| device-local-ehub-wloadprodq-l2   | Number:Energy           | R          |                                          |
| device-local-ehub-wloadprodq-l3   | Number:Energy           | R          |                                          |
| device-local-ehub-ppv             | Number:Power            | R          | Only sent when system has PV             |
| device-local-ehub-pinv-l1         | Number:Power            | R          | Inverter power, active L1                |
| device-local-ehub-pinv-l2         | Number:Power            | R          | Inverter power, active L2                |
| device-local-ehub-pinv-l3         | Number:Power            | R          | Inverter power, active L3                |
| device-local-ehub-iextq-l1        | Number:ElectricCurrent  | R          | External/grid active current L1          |
| device-local-ehub-iextq-l2        | Number:ElectricCurrent  | R          | External/grid active current L2          |
| device-local-ehub-iextq-l3        | Number:ElectricCurrent  | R          | External/grid active current L3          |
| device-local-ehub-pext-l1         | Number:Power            | R          | External/grid power, active L1           |
| device-local-ehub-pext-l2         | Number:Power            | R          | External/grid power, active L2           |
| device-local-ehub-pext-l3         | Number:Power            | R          | External/grid power, active L3           |
| device-local-ehub-wextprodq-l1    | Number:Energy           | R          |                                          |
| device-local-ehub-wextprodq-l2    | Number:Energy           | R          |                                          |
| device-local-ehub-wextprodq-l3    | Number:Energy           | R          |                                          |
| device-local-ehub-wpv             | Number:Energy           | R          | Only sent when system has PV             |
| device-local-ehub-pextreactive-l1 | Number:Power            | R          | External/grid power, Reactive L1         |
| device-local-ehub-pextreactive-l2 | Number:Power            | R          | External/grid power, Reactive L2         |
| device-local-ehub-pextreactive-l3 | Number:Power            | R          | External/grid power, Reactive L3         |
| device-local-ehub-udcpos          | Number:ElectricPotential| R          | Positiv link voltage                     |
| device-local-ehub-udcneg          | Number:ElectricPotential| R          | Negativ DC link voltage                  |
| device-local-ehub-sext            | Number:Energy           | R          | Apparent power                           |
| device-local-ehub-iextd-l1        | Number:ElectricCurrent  | R          | External/grid Reactive current L1        |
| device-local-ehub-iextd-l2        | Number:ElectricCurrent  | R          | External/grid Reactive current L2        |
| device-local-ehub-iextd-l3        | Number:ElectricCurrent  | R          | External/grid Reactive current L3        |
| device-local-ehub-wextconsq_3p    | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-ild-l1          | Number:ElectricCurrent  | R          | Inverter Reactive current L1             |
| device-local-ehub-ild-l2          | Number:ElectricCurrent  | R          | Inverter Reactive current L2             |
| device-local-ehub-ild-l3          | Number:ElectricCurrent  | R          | Inverter Reactive current L3             |
| device-local-ehub-gridfreq        | Number:Frequency        | R          | Estimated Grid Frequency                 |
| device-local-ehub-wloadconsq_3p   | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-ul-l1           | Number:ElectricPotential| R          | External voltage L1                      |
| device-local-ehub-ul-l2           | Number:ElectricPotential| R          | External voltage L2                      |
| device-local-ehub-ul-l3           | Number:ElectricPotential| R          | External voltage L3                      |
| device-local-ehub-wextprodq_3p    | Number:ElectricCurrent  | R          |                                          |
| device-local-ehub-ilq-l1          | Number:ElectricCurrent  | R          | Inverter active current L1               |
| device-local-ehub-ilq-l2          | Number:ElectricCurrent  | R          | Inverter active current L2               |
| device-local-ehub-ilq-l3          | Number:ElectricCurrent  | R          | Inverter active current L3               |
| device-local-ehub-winvprodq-l1    | Number:Energy           | R          |                                          |
| device-local-ehub-winvprodq-l2    | Number:Energy           | R          |                                          |
| device-local-ehub-winvprodq-l3    | Number:Energy           | R          |                                          |
| device-local-ehub-il-l1           | Number:ElectricCurrent  | R          | Inverter RMS current L1                  |
| device-local-ehub-il-l2           | Number:ElectricCurrent  | R          | Inverter RMS current L2                  |
| device-local-ehub-il-l3           | Number:ElectricCurrent  | R          | Inverter RMS current L3                  |
| device-local-ehub-wbatprod        | Number:Energy           | R          | Only sent when system has batteries      |
| device-local-ehub-wpbatcons       | Number:Energy           | R          | Only sent when system has batteries      |
| device-local-ehub-soc             | Number:Dimensionless    | R          | State Of Charge for the system           |
| device-local-ehub-soh             | Number:Dimensionless    | R          | State Of Health for the system           |
| device-local-ehub-pbat            | Number:Power            | R          | Only sent when system has batteries      |
| device-local-ehub-ratedcap        | Number:Energy           | R          | Total rated capacity of all batteries in system|
| device-local-ssos0-relaystatus    | String                  | R          | 0 = relay closed (i.e running power), 1 = relay open/disconnected, 2 = precharge|
| device-local-ssos0-temp           | Number:Temperature      | R          | Temperature measured on PCB of SSO-0     |
| device-local-ssos0-wpv            | Number:Energy           | R          | Total energy produced by SSO-0           |
| device-local-ssos0-ts             | String                  | R          | Time stamp when message was published    |
| device-local-ssos0-udc            | Number:ElectricPotential| R          | DC link voltage as measured by SSO-0     |
| device-local-ssos0-faultcode      | String                  | R          | See section 4.1.3.1                      |
| device-local-ssos0-ipv            | Number:ElectricCurrent  | R          | Measured on PV string side               |
| device-local-ssos0-upv            | Number:ElectricPotential| R          | Measured on PV string side               |
| device-local-ssos0-id             | String                  | R          | Unique identifier of SSO-0               |
| device-local-ssos1-relaystatus    | String                  | R          | 0 = relay closed (i.e running power), 1 = relay open/disconnected, 2 = precharge|
| device-local-ssos1-temp           | Number:Temperature      | R          | Temperature measured on PCB of SSO-1     |
| device-local-ssos1-wpv            | Number:Energy           | R          | Total energy produced by SSO-1           |
| device-local-ssos1-ts             | String                  | R          | Time stamp when message was published    |
| device-local-ssos1-udc            | Number:ElectricPotential| R          | DC link voltage as measured by SSO-1     |
| device-local-ssos1-faultcode      | String                  | R          | See section 4.1.3.1                      |
| device-local-ssos1-ipv            | Number:ElectricCurrent  | R          | Measured on PV string side               |
| device-local-ssos1-upv            | Number:ElectricPotential| R          | Measured on PV string side               |
| device-local-ssos1-id             | String                  | R          | Unique identifier of SSO-1               |
| device-local-ssos2-relaystatus    | String                  | R          | 0 = relay closed (i.e running power), 1 = relay open/disconnected, 2 = precharge|
| device-local-ssos2-temp           | Number:Temperature      | R          | Temperature measured on PCB of SSO-2     |
| device-local-ssos2-wpv            | Number:Energy           | R          | Total energy produced by SSO-2           |
| device-local-ssos2-ts             | String                  | R          | Time stamp when message was published    |
| device-local-ssos2-udc            | Number:ElectricPotential| R          | DC link voltage as measured by SSO-2     |
| device-local-ssos2-faultcode      | String                  | R          | See section 4.1.3.1                      |
| device-local-ssos2-ipv            | Number:ElectricCurrent  | R          | Measured on PV string side               |
| device-local-ssos2-upv            | Number:ElectricPotential| R          | Measured on PV string side               |
| device-local-ssos2-id             | String                  | R          | Unique identifier of SSO-2               |
| device-local-ssos3-relaystatus    | String                  | R          | 0 = relay closed (i.e running power), 1 = relay open/disconnected, 2 = precharge|
| device-local-ssos3-temp           | Number:Temperature      | R          | Temperature measured on PCB of SSO-3     |
| device-local-ssos3-wpv            | Number:Energy           | R          | Total energy produced by SSO-3           |
| device-local-ssos3-ts             | String                  | R          | Time stamp when message was published    |
| device-local-ssos3-udc            | Number:ElectricPotential| R          | DC link voltage as measured by SSO-3     |
| device-local-ssos3-faultcode      | String                  | R          | See section 4.1.3.1                      |
| device-local-ssos3-ipv            | Number:ElectricCurrent  | R          | Measured on PV string side               |
| device-local-ssos3-upv            | Number:ElectricPotential| R          | Measured on PV string side               |
| device-local-ssos3-id             | String                  | R          | Unique identifier of SSO-3               |
| device-local-eso-faultcode        | String                  | R          | See section 4.1.3.1                      |
| device-local-eso-id               | String                  | R          | Unique identifier                        |
| device-local-eso-ibat             | Number:ElectricCurrent  | R          | Measured on battery side                 |
| device-local-eso-ubat             | Number:ElectricPotential| R          | Measured on battery side                 |
| device-local-eso-relaystatus      | String                  | R          | 0 = relay closed (i.e running power), 1 = relay open/disconnected, 2 = precharge|
| device-local-eso-soc              | Number:Dimensionless    | R          | State of Charge for ESO                  |
| device-local-eso-temp             | Number:Temperature      | R          | Measured inside ESO                      |
| device-local-eso-wpbatcons        | Number:Energy           | R          | Total energy produced by ESO, i.e total energy charged|
| device-local-eso-wbatprod         | Number:Energy           | R          | Total energy produced by ESO, i.e total energy discharged|
| device-local-eso-udc              | Number:Power            | R          | DC link voltage as measured by ESO       |
| device-local-eso-ts               | String                  | R          | Time stamp when message was published    |
| device-local-esm-soh              | Number:Dimensionless    | R          |                                          |
| device-local-esm-soc              | Number:Dimensionless    | R          |                                          |
| device-local-esm-rated-capacity   | Number:Energy           | R          | Rated capacity of battery                |
| device-local-esm-id               | String                  | R          | Unique identifier of battery. If available, this will be the unique id that the battery reports. |
| device-local-esm-rated-power      | Number:Power            | R          | Rated power of battery                   |
| device-local-esm-status           | String                  | R          | Dependent on battery manufacturer        |
| device-local-esm-ts               | String                  | R          | Time stamp when message was published    |
  

