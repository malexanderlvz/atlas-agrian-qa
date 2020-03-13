
# Atlas/Agrian Intergration

**NOTE:** The existing functionality was developed based off the provided Agrian documentation.

Supported functionality as of `3/12/2020` testing

* [Create Grower](#create-grower)
* [Update Grower](#update-grower)
* [Create Farm](#create-farm)
* [Create Field](#create-field)
* [Update Field](#update-field)
* [Create Plantings](#create-planting)

## **Create Grower**

To create a new Grower change the following fields

* `COMPANY_NAME`
* `GROWER_NUMBER`
* `RCH_STREET_ADDRESS`
* `RCH_STREET_ADDRESS_2`
* `RCH_LOCALITY`
* `RCH_POSTAL_CODE`
* `RANCH_LATITUDE`
* `RANCH_LONGITUDE`

```json
{
    "properties": {
        "COMPANY_NAME": "13 Disney Test",
        "GROWER_NUMBER": 777777,
        "RCH_STREET_ADDRESS": "1313 Disneyland Dr",
        "RCH_STREET_ADDRESS_2": "APT #13",
        "RCH_LOCALITY": "Anaheim",
        "RCH_POSTAL_CODE": "92802",
        "RANCH_LATITUDE": 33.812137,
        "RANCH_LONGITUDE": -117.918967,
```

### **Results**

**Results based on [0_grower-create.json](json/0_grower-create.json) input.**

| Agrian UI         |   JSON                | Results            |
| ----------------- | -----------------     | -------------------|
| Name              | COMPANY_NAME          | 13 Disney Test     |
| Code              | GROWER_NUMBER         | 777777             |
| Account Number    | GROWER_NUMBER         | 777777             |
| Status            |                       | Active             |
| Country           |                       | Brazil             |
| Street 1          | RCH_STREET_ADDRESS    | 1313 Disneyland Dr |
| Street 2          | RCH_STREET_ADDRESS_2  | APT #13            |
| City              | RCH_LOCALITY          | Anaheim            |
| State / Province  |                       |                    |
| Postal Code       | RCH_POSTAL_CODE       | 92802              |
| Latitude          | RANCH_LATITUDE        | 33.812137          |
| Longitude         | RANCH_LONGITUDE       | -117.918967        |

![grower-create-0](/screenshots/0_grower-create-0.png?raw=true)
![grower-create-1](/screenshots/0_grower-create-1.png?raw=true)
![grower-create-2](/screenshots/0_grower-create-2.png?raw=true)

## **Update Grower**

To update a Grower leave the existing `COMPANY_NAME` of the Grower you'd like to update & change the following fields

* `COMPANY_NAME`
* `RCH_STREET_ADDRESS`
* `RCH_STREET_ADDRESS_2`
* `RCH_LOCALITY`
* `RCH_POSTAL_CODE`
* `RANCH_LATITUDE`
* `RANCH_LONGITUDE`

```json
{
    "properties": {
        "COMPANY_NAME": "13 Disney Test",
        "GROWER_NUMBER": 333333,
        "RCH_STREET_ADDRESS": "1401 N Shoreline Blvd",
        "RCH_STREET_ADDRESS_2": "OFC #33",
        "RCH_LOCALITY": "Mountain View",
        "RCH_POSTAL_CODE": "94043",
        "RANCH_LATITUDE": 37.415178,
        "RANCH_LONGITUDE": -122.077237,
```
### **Results**

**Results based on [1_grower-update.json](json/1_grower-update.json) input.**

| Agrian UI         |   JSON Varible        | Old Results           | Updated Results       |
| ----------------- | -----------------     | -----------------     | -----------------     |
| Name              | COMPANY_NAME          | 13 Disney Test        | 13 Disney Test        |
| Code              | GROWER_NUMBER         | 777777                | 333333                |
| Account Number    | GROWER_NUMBER         | 777777                | 333333                |
| Status            |                       | Active                | Active                |
| Country           |                       | Brazil                | Brazil                |
| Street 1          | RCH_STREET_ADDRESS    | 1313 Disneyland Dr    | 1401 N Shoreline Blvd |
| Street 2          | RCH_STREET_ADDRESS_2  | APT #13               | OFC #33               |
| City              | RCH_LOCALITY          | Anaheim               | Mountain View         |
| State / Province  |                       |                       |                       |
| Postal Code       | RCH_POSTAL_CODE       | 92802                 | 94043                 |
| Latitude          | RANCH_LATITUDE        | 33.812137             | 37.415178             |
| Longitude         | RANCH_LONGITUDE       | -117.918967           | -122.077237           |

![grower-update-0](/screenshots/1_grower-update-0.png?raw=true)
![grower-update-1](/screenshots/1_grower-update-1.png?raw=true)
![grower-update-2](/screenshots/1_grower-update-2.png?raw=true)

## **Create New Farm**

To create a new Farm leave the existing `COMPANY_NAME` & change

* `RANCH_NAME`

```json
{
    "properties": {
        "RANCH_NAME": "Seven Eight #9",
```
### **Results**

**Results based on [2_farm-create.json](json/2_farm-create.json) input.**


| Agrian UI         |   JSON                | Results               |
| ----------------- | -----------------     | -----------------     |
| Name              | RANCH_NAME            | Seven Eight #9        |
| Code              | RANCH_NAME            | Seven Eight #9        |
| Status            |                       | Active                |
| Latitude          |                       |                       |
| Longitude         |                       |                       |

![farm-create-0](/screenshots/2_farm-create-0.png?raw=true)
![farm-create-1](/screenshots/2_farm-create-1.png?raw=true)

## **Create New Field**

To create a new Field leave the existing `COMPANY_NAME` & `RANCH_NAME` and change

* `TRANSACTIONAL_RANCH_NAME`
* `TRANSACTIONAL_RANCH_NUMBER`
* `HECTARES`
* `RANCH_LATITUDE`
* `RANCH_LONGITUDE`

```json
{
    "properties": {
        "TRANSACTIONAL_RANCH_NAME": "LeftField Test #1",
        "TRANSACTIONAL_RANCH_NUMBER": 1313,
        "HECTARES": 1.94042370123863,
        "RANCH_LATITUDE": 37.415178,
        "RANCH_LONGITUDE": -122.077237,
````
### **Results**

**Results based on [3_field-create.json](json/3_field-create.json) input.**

| Agrian UI             | JSON                       | Results               |
| -----------------     | -----------------          | -----------------     |
| Name                  | TRANSACTIONAL_RANCH_NAME   | LeftField Test #1     |
| Code                  | TRANSACTIONAL_RANCH_NUMBER | 1313                  |
| Field Size            | HECTARES                   | 1.94042370123863      |
| Status                |                            | Active                |
| Growing Method        |                            | Conventional          |
| State / Province      |                            | Acre                  |
| County                |                            |                       |
| Location Description  |                            |                       |
| Latitude              | RANCH_LATITUDE             | 37.415178             |
| Longitude             | RANCH_LONGITUDE            | -122.077237           |
| Section               |                            |                       |
| Township              |                            |                       |
| Range                 |                            |                       |
| Baseline              |                            |                       |
| Commodity             |                            | Raspberry             |

![field-create-0](/screenshots/3_field-create-0.png?raw=true)
![field-create-1](/screenshots/3_field-create-1.png?raw=true)
![field-create-2](/screenshots/3_field-create-2.png?raw=true)

## **Update Field**

To update an existing Field leave the existing `COMPANY_NAME` & `RANCH_NAME` and change

* `TRANSACTIONAL_RANCH_NUMBER`
* `HECTARES`
* `RANCH_LATITUDE`
* `RANCH_LONGITUDE`

```json
{
    "properties": {
        "TRANSACTIONAL_RANCH_NUMBER": 7777,
        "HECTARES": 5.1,
        "RANCH_LATITUDE": 37.233333,
        "RANCH_LONGITUDE": -115.808333,
````

### **Results**

**Results based on [4_field-update.json](json/4_field-update.json) input.**

| Agrian UI             | JSON                       | Old Results           | Updated Results      |
| -----------------     | -----------------          | -----------------     | -----------------    |
| Name                  | TRANSACTIONAL_RANCH_NAME   | LeftField Test #1     | LeftField Test #1    |
| Code                  | TRANSACTIONAL_RANCH_NUMBER | 1313                  | 7777                 |
| Field Size            | HECTARES                   | 1.94042370123863      | 5.1                  |
| Status                |                            | Active                | Active               |
| Growing Method        |                            | Conventional          | Conventional         |
| State / Province      |                            | Acre                  | Acre                 |
| County                |                            |                       |                      |
| Location Description  |                            |                       |                      |
| Latitude              | RANCH_LATITUDE             | 19.315073             | 37.233333            |
| Longitude             | RANCH_LONGITUDE            | -103.371444           | -115.808333          |
| Section               |                            |                       |                      |
| Township              |                            |                       |                      |
| Range                 |                            |                       |                      |
| Baseline              |                            |                       |                      |
| Commodity             |                            | Raspberry             | Raspberry            |

![field-update-0](/screenshots/4_field-update-0.png?raw=true)
![field-update-1](/screenshots/4_field-update-1.png?raw=true)
![field-update-2](/screenshots/4_field-update-2.png?raw=true)

## **PLANTINGS**

### ***Testing...***