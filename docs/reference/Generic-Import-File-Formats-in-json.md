---
tags:
  - Member Database
---
## Overview

Sqorz defines two generic file formats for importing event entries and member databases.

We specify JSON formatted files containing an array of objects with fields defined below. 
File name and field order are not important. Fields that are not required and unused 
may be omitted entirely. See attached examples.

Custom file formats are also available upon request.

## Members
Import your member database into Sqorz using this file format. 

## Member Object
The following fields are defined:

| Field Name | Required | Format | Sample Value   | Notes |
| --- | --- | --- |----------------|-------|
|familyName	|Y	|string	| Smith          |       |	
|givenName	|Y	|string	| Jane           |       |	
|birthDate	|Y	|YYYY-MM-DD	| 2000-12-31     |       |	
|gender	|Y	|string| FEMALE<br>MAIL | 1     |
|plate	|Y	|string	| 123            |	
|transponders	|N	|array of Transponder Objects| See below      |
|nationalLicenseType	|N	|string | AU             |2|
|nationalLicenseClass	|N	|string| OPEN           |2|
|nationalLicenseNumber	|Y	|string	| 123456         |	
|nationalLicenseExpiryDate	|N	|YYYY-MM-DD	| 2020-12-31     |	
|globalLicenseType	|N	|string	| UCI	           |2|
|globalLicenseClass	|N	|string	| OPEN	          |2|
|globalLicenseNumber	|N	|string	| 1234567890	    |2|
|globalLicenseExpiryDate	|N	|YYYY-MM-DD	| 2020-12-31     ||	

### Transponder Object


| Field Name | Required | Format | Sample Value                           | Notes |
| --- | --- | --- |----------------------------------------|-------|
|transponder	|Y	|string	| AB-12345                               ||	
|classType	|Y	|string| 20 (BMX 20" bike)<br>20 (BMX 24" bike) |1|

## Entries
Import entries into an event using this file format. Can also be used to load the member database.

For competitors entering more than one class, repeat the record as required with changed className.

## Entry Object
The entries file extends the member file format with the following additional fields:

| Field Name | Required | Format | Sample Value                           | Notes |
| --- | --- | --- |----------------------------------------|-------|
|className	|Y	|string|8 Boys<br>9 Girls|2|
|classPlate	|N	|string	|123||	
|classTransponder	|N	|string	|AB-12345||	
|classHireTransponder	|N	|boolean|true<br>false|Cannot be true if classTransponder specified.|

## Notes

1. Case-insensitive
2. Depends on sport and region. Values to be agreed with EventSoft.

## Sample Files

- [generic-entries.json](Generic-Import-File-Formats-in-json-assets/generic-entries.json)
- [generic-members.json](Generic-Import-File-Formats-in-json-assets/generic-members.json)
    