# Introduction

This is a Data Science Challenge issued by:

>Dr. Roland Stoffel,
>DSA Daten- und Systemtechnik GmbH
>Business Unit SKYLYZE
>Ferdinand-Sauerbruch-Str. 27, 56073 Koblenz, Germany
>http://www.skylyze.com

It was sucessfully completed using different data analysis teqniques.

All the data for this challenge was generated and not real in any case.

# Warranty Test Environment

## Storyline

The automotive manufacturer "Only Excellent Machines (OEM)" produces around x vehicle per month. The different vehicle types are produced based on the following distribution:

| Vehicle Type | Code | Production [%] |
|--------------|------|----------------|
| car | vt1 | |
| city cruiser | vt2 | |
| suv | vt3 | |
| sports-car | vt4 | |

Furthermore the vehicles are delivered to the markets (in %):

| Vehicle Type | DE | EU | US | BR | CN |
|--------------|----|----|----|----|----|
| car |  |  |  |  |  |
| city cruiser |  |  |  |  | |
| suv | | | | | |
| sports-car | | | | | |

In addition, the vehicles are equipped with different engines and transmissions (in %):

| Vehicle Type | e1 | e2 | e3 | e4 |
|--------------|----|----|----|----|
| car | | | | |
| city cruiser | | | | |
| suv | | | | |
| sports-car | | | | |

| Vehicle Type | tr1 | tr2 |
|--------------|-----|-----|
| car | | |
| city cruiser | | |
| suv | | |
| sports-car | | |

The supplier "Super Useful Products (SUP)" produces windows lifting systems (wls):

| window lifting system | group | description |
|-----------------------|-------|-------------|
| wlsre01l | regular wls | normal system (left) |
| wlsre01r | regular wls | normal system (right) |
| wlssr01t | sliding roof | sliding roof |
| wlssp01l | special design | protective glass (left) |
| wlssp01r | special design | protective glass (right) |

The systems are assembled to the different vehicle types with the following quotes (in %):

| Vehicle Type | regular wls | special design | sliding roof |
|--------------|-------------|----------------|--------------|
| car | | | |
| city cruiser | | | |
| suv | | | |
| sports-car | | | |

| window lifting system | car | city cruiser | suv | sports-car |
|-----------------------|-----|--------------|-----|------------|
| wlsre01l | | | | |
| wlsre01r | | | | |
| wlsre01t | | | | |
| wlssp01l | | | | |
| wlssp01r | | | | |

In addition, the number of parts installed into the different vehicle types is as follows

| window lifting system | car | city cruiser | suv | sports-car |
|-----------------------|-----|--------------|-----|------------|
| wlsre01l | 2 | 1 | 2 | 1 |
| wlsre01r | 2 | 1 | 2 | 1 |
| wlsre02t | max 1 | 0 | max 1 | 0 |
| wlssp01l | 2 | 0 | 2 | 0 |
| wlssp01r | 2 | 0 | 2 | 0 |

A warranty contract exists between OEM and SUP, whereby the warranty period is set to 48 months for all products. As a rule, the warranty starts with the first registration of the vehicle, whereby the delay between the production date and the start of the warranty consists of delivery time + storage time + sale and first registration. Warranty cases that arise during transport or production up to the initial notification are referred to as 0-KM cases and are considered separately. The failure date in the field is assumed to be the time of repair. The time-in-service is assumed to be the days between registration and repair date, notated as dis. Another representation of the time-in-service is often month-in-service (mis), which is only a monthly view. Furthermore, the creation of the debit note by the OEM is assumed as the invoice date. Since the repartition message must first be reported to the OEM, there is also a delay between the repair date and the invoice date, which is usually only a few days. The debit notes are then not transmitted individually from OEM to SUP, but are forwarded collectively to SUP per month. After reviewing the complaint cases, SUP has the possibility to file an appeal for such cases. All in all, the complaints are objected to, checked and sifted on a monthly basis. The final total amount to be reimbursed is then negotiated at the end of a fiscal year on the basis of the monthly complaint reports between the SUP and the OEM.

A standard complaint is usually due to the following causes

| failure code | text |  
|--------------|------|
| f0001 | noise |
| f0002 | material break |
| f0003 | mechanical failure |
| f0004 | electric failure |
| f0005 | unknown |

The failure distribution depends on different correlations

| Vehicle Type | f0001 | f0002 | f0003 | f0004 | f0005 |  
|--------------|-------|-------|-------|-------|-------|
| vt1 |  |  |  |  |  |
| vt2 |  |  |  |  |  |
| vt3 |  |  |  |  |  |
| vt4 |  |  |  |  |  |

| Country | f0001 | f0002 | f0003 | f0004 | f0005 |  
|---------|-------|-------|-------|-------|-------|
| DE |  |  |  |  |  |
| EU |  |  |  |  |  |
| US |  |  |  |  |  |
| BR |  |  |  |  |  |
| CN |  |  |  |  |  |

## Challenge

The data contains the claim data respectively debit notes, which are sent from OEM to SUP with respect to the production of SUP from 2010. The challange is to find the distributions and other interesting statistics (be creative) which lies inside the data. Furthermore present the results in an analysis report.

In addition the failure behavior ("When does my parts of a production fail?" --> time-in-service) is based on a Weibull distribution and is constant for a monthly production of a windows system. In example the sum of produced parts of wlsre01l in May 2010 behave on the same distribution. From business management view a company is very interested in the failure behavior of parts which will be produced in the future. How can the data be used to predict their failure/repair dates, e.g. if it is assumed that 1000 parts are produced in January 2019.



