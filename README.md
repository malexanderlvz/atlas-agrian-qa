
# Atlas/Agrian Intergration API Examples

The file `atlas-exp-body.json` contains a example input body.

We must still include the following top portion of our JSON body, even though we're only changing the "Properties".

```json
{
  "type": "FeatureCollection",
  "features": [
    {
        "type": "Feature",
        "id": 37601,
        "geometry": {...
        },
```

## **Create a new Grower**

- Change `COMPANY_NAME` to a desired Grower Name
- Change `GROWER_NUMBER` to a unique Grower Account Number
- Change `RCH_STREET_ADDRESS` to a desired Grower Street 1
- Change `RCH_STREET_ADDRESS_2` to a desired Grower Street 2
- Change `RCH_LOCALITY` to a desired Grower City
- Change `RCH_POSTAL_CODE` to a desitred Grower Postal Code
- Change `RANCH_LATITUDE` to a desired Grower Location Latitude
- Change `RANCH_LONGITUDE` to a desired Grower Location Longitude

```json
{
    "properties": {
        "COMPANY_NAME": "Test Grower Name, LLC",
        "GROWER_NUMBER": 999101,
        "RCH_STREET_ADDRESS": "2310 S Forbes Rd",
        "RCH_STREET_ADDRESS_2": "#1",
        "RCH_LOCALITY": "Plant City",
        "RCH_POSTAL_CODE": "33566",
        "RANCH_LATITUDE": 27.987167575000058,
        "RANCH_LONGITUDE": -82.187056261999942,
```

### **Grower**

| Agrian UI         |   JSON                | Example               |
| ----------------- | -----------------     | -----------------     |
| Name              | COMPANY_NAME          | Test Grower Name, LLC |
| Code              | COMPANY_NAME          | Test Grower Name, LLC |
| Account Number    | GROWER_NUMBER         | 999101                |
| Status            |                       | Active                |
| Country           |                       | Mexico                |
| Street 1          | RCH_STREET_ADDRESS    | 2310 S Forbes Rd      |
| Street 2          | RCH_STREET_ADDRESS_2  | Room 207              |
| City              | RCH_LOCALITY          | Plant City            |
| State / Province  |                       | Jalisco               |
| Postal Code       | RCH_POSTAL_CODE       | 33566                 |
| Latitude          | RANCH_LATITUDE        | 27.987167575000058    |
| Longitude         | RANCH_LONGITUDE       | -82.187056261999942   |

## **Update Existing Grower**

Enter the existing `GROWER_NUMBER` of the Grower you'd like to update; in this example we kept it the same.

Change any of the following fields to update your Grower:

- `COMPANY_NAME`
- `RCH_STREET_ADDRESS`
- `RCH_STREET_ADDRESS_2`
- `RCH_LOCALITY`
- `RCH_POSTAL_CODE`
- `RANCH_LATITUDE`
- `RANCH_LONGITUDE`

```json
{
    "properties": {
        "COMPANY_NAME": "New Name, LLC",
        "GROWER_NUMBER": 999101,
        "RCH_STREET_ADDRESS": "1234 New Way Rd.",
        "RCH_STREET_ADDRESS_2": "OFC #321",
        "RCH_LOCALITY": "New City",
        "RCH_POSTAL_CODE": "12345",
        "RANCH_LATITUDE": 33.812511,
        "RANCH_LONGITUDE": -117.918976,
```

### **Grower**

| Agrian UI         |   JSON Varible        | Old Fields            | Updated Example       |
| ----------------- | -----------------     | -----------------     | -----------------     |
| Name              | COMPANY_NAME          | Test Grower Name, LLC | New Name, LLC         |
| Code              | COMPANY_NAME          | Test Grower Name, LLC | New Name, LLC         |
| Account Number    | GROWER_NUMBER         | 999101                | 999101                |
| Status            |                       | Active                | Active                |
| Country           |                       | Mexico                | Mexico                |
| Street 1          | RCH_STREET_ADDRESS    | 2310 S Forbes Rd      | 1234 New Way Rd.      |
| Street 2          | RCH_STREET_ADDRESS_2  | ROOM #207             | OFC #321              |
| City              | RCH_LOCALITY          | Plant City            | New City              |
| State / Province  |                       | Jalisco               | Jalisco               |
| Postal Code       | RCH_POSTAL_CODE       | 33566                 | 12345                 |
| Latitude          | RANCH_LATITUDE        | 27.987167575000058    | 33.812511             |
| Longitude         | RANCH_LONGITUDE       | -82.187056261999942   | -117.918976           |

## **Create a new Farm**

After your Grower is created, create a new Farm by setting a uniuqe `RANCH_NAME`.

```json
{
    "properties": {
        "RANCH_NAME": "Test Ranch #1",
```

### **Farm**

| Agrian UI         |   JSON                | Example               |
| ----------------- | -----------------     | -----------------     |
| Name              | RANCH_NAME            | Test Ranch #1         |
| Code              | RANCH_NAME            | Test Ranch #1         |
| Status            |                       | Active                |
| Latitude          |                       |                       |
| Longitude         |                       |                       |

## **Creating New Field**

After your Ranch is created, enter a unique `CUSTOMS_NAME` to create a new Field.

### **WORKING**

```json
{
    "properties": {
        "CUSTOMS_NAME": "WP20",
````

### **NEEDS WORK**

```json
{
    "properties": {
        "RANCH_LATITUDE": 33.812511,
        "RANCH_LONGITUDE": -117.918976,
        "MEDIA": "Conventional",
        "HECTARES": 2.42,
```

- Changing **RANCH_LATITUDE** doesn't seem to affect **Latitude**</br>...it seems set to `19.315073` by default

- Changing **RANCH_LONGITUDE** doesn't seem to affect **Logitude**</br>...it seems set to `-103.371444` by default

- Changing **MEDIA** doesn't seem to affect **Growing Method**</br>...it seems set to `Conventional` by default

- Changing **HECTARES** doesn't seem to affect **Field Size**</br> ...it seems set to `2.42` by default

### **Field**

| Agrian UI             | JSON                  | Example               |
| -----------------     | -----------------     | -----------------     |
| Name                  | CUSTOMS_NAME          | WP20                  |
| Code                  | CUSTOMS_NAME          | WP20                  |
| Field Size            |                       | 2.42                  |
| Status                |                       | Active                |
| Growing Method        |                       | Conventional          |
| State / Province      |                       | Jalisco               |
| County                |                       |                       |
| Location Description  |                       |                       |
| Latitude              |                       | 19.315073             |
| Longitude             |                       | -103.371444           |
| Section               |                       |                       |
| Township              |                       |                       |
| Range                 |                       |                       |
| Baseline              |                       |                       |

### **PLANTINGS**

Input as per developer. This is currently being tested.

```json
{
    "properties": {
        "FRUITING_CYCLE_END_DATE": "2020-2-2",
        "IS_ACTIVE": "Yes",
        "HECTARES": 1.25,
        "APPLICATION_BLOCK_CODE": "A1",
        "PLANT_YEAR_GROUPING": 2020,
        "PLANTING_DATE": "2020-1-01",
        "VARIETY": "KIRRA",
        "BERRY_TYPE": "RASP",
        "VARIETY_ID": "V9J",
```

----

| Agrian UI             | JSON                  | Example               |
| -----------------     | -----------------     | -----------------     |
| Season Start          |                       |                       |
| Season End            |                       |                       |
| Commodity             |                       |                       |
| Variety               |                       |                       |
| Name | APPLICATION_BLOCK_CODE + PLANT_YEAR_GROUPING + VARIETY | A12020KIRRA |
| Code | APPLICATION_BLOCK_CODE + PLANT_YEAR_GROUPING + VARIETY | A12020KIRRA |
| Field                 |                       |                       |
| Date Planted          | PLANTING_DATE         | 01/01/2020            |
| Planting Size         | HECTARES              | 1.25                  |
| Traits                |                       |                       |
| Growing Medium        |                       |                       |
| Planting Method       |                       |                       |
| Growing Method        |                       |                       |
| Tillage Type          |                       |                       |
| Intended Use          |                       |                       |
| Status                |                       |                       |
| Latitude              |                       | 19.31527              |
| Longitude             |                       | -103.3715579631513    |

- Seems Latitude is set to `19.315073` by default

- Seems Longitude is set to `-103.371444` by default

#### **NOTES**

- As of right now County & States are only applicable to Mexico. Work is being done on US IDs; they will be genrated based on the incoming Atlas payload.

- Updating Farms, Fields, & Plantings is not yet ready.
