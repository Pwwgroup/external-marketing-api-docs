# Marketing External API - MIGHTY

## Links

[Create Lead](#create-lead)

## <a name="create-lead"></a>Create Lead

**Method: POST**

**Test-URL:** https://staging.greenpoweradvice.co.uk/api/marketing

**Live-URL:** https://www.greenpoweradvice.co.uk/api/marketing

**URL Prefix:** /v1/mighty/lead

**URL Params:**

```JSON
N/A
```

**URL Query Params:**

```JSON
N/A
```

**Headers:**

```JSON
token: 123456789
```

**Body Full**

```JSON
{
    "energyType": "Both",
    "gasSupplier": "British Gas",
    "electricitySupplier": "-none-",
    "businessName": "Utility Locker",
    "street": "18 School Ln",
    "postcode": "L13BT",
    "city": "Liverpool",
    "fullName": "Thomas Dittmer",
    "email": "shuanking678@test.com",
    "mobile": "07981231234",
    "gasRenewalDate": "10-2021",
    "electricityRenewalDate": "10-2021",
    "gasSpend": "3000",
    "electricitySpend": "3000",
    "notes": "test note"
}
```

**Body partial**

```JSON
{
    "energyType": "Both",
    "gasSupplier": "British Gas",
    "electricitySupplier": "-none-",
    "businessName": "Utility Locker",
    "street": "18 School Ln",
    "postcode": "L13BT",
    "city": "Liverpool",
    "fullName": "Thomas Dittmer",
    "email": "shuanking678@test.com",
    "mobile": "07981231234"
}
```

#### Valid Suppliers

**<a name="gas"></a>gas**

```JSON
[
  "-None-",
  "Dual",
  "Crown Gas & Power",
  "GDF Suez",
  "BES",
  "Axis",
  "British Gas Business",
  "CNG",
  "Corona Energy",
  "Dong Energy/Orsted",
  "E.ON",
  "Ecotricity",
  "EDF",
  "Enterprise Gas",
  "Extra Energy",
  "First Utility",
  "Gazprom Energy",
  "Good Energy",
  "Haven Power",
  "Hudson Energy",
  "LoCO2 Energy",
  "N-Power",
  "Opus Energy",
  "Ovo Energy",
  "Regent Gas",
  "Scottish Power",
  "SmartestEnergy",
  "SSE",
  "Total Gas & Power",
  "United Gas & Power",
  "WINGAS",
  "Yorkshire Gas & Power",
  "Yu Energy",
  "Utility Warehouse",
  "BG Corp.",
  "BG SME",
  "Scottish Gas",
  "One Energy",
  "NEPO",
  "Economy Gas Ltd",
  "D-Energi",
  "ME Energy",
  "The Gas Company",
  "Utilita",
  "Prime Gas and Power",
  "Solarplicity",
  "PFP Energy",
  "Valda Energy",
];
```

**<a name="elec"></a>elec**

```JSON
[
  "-None-",
  "Axis",
  "BES",
  "BG Corp",
  "BG SME",
  "British Gas Business",
  "CNG",
  "Corona Energy",
  "Crown Gas & Power",
  "Dong Energy/Orsted",
  "Dual",
  "E.ON",
  "Ecotricity",
  "EDF",
  "Enterprise Gas",
  "Extra Energy",
  "First Utility",
  "Gazprom Energy",
  "GDF Suez",
  "Good Energy",
  "Haven Power",
  "Hudson Energy",
  "LoCO2 Energy",
  "N-Power",
  "Opus Energy",
  "Ovo Energy",
  "Regent Gas",
  "Scottish Power",
  "SmartestEnergy",
  "SSE",
  "Total Gas & Power",
  "United Gas & Power",
  "Utility Warehouse",
  "WINGAS",
  "Yorkshire Gas & Power",
  "Yu Energy",
  "One Energy",
  "NEPO",
  "D-Energi",
  "Unicom",
  "The Gas Company",
  "Utilita",
  "Western Power",
  "F&S Energy",
  "Npower Corp.",
  "Prime Gas and Power",
  "Solarplicity",
  "PFP Energy",
  "Valda Energy",
  "Bryt Energy",
];
```

**Field Rules**
| Field | Required | Rule |
| :----------- | :--------: | -----------: |
| businessOwner | Y | 1 Characters Max |
| energyType | Y | ('electricity', 'gas', 'both') |
| gasSupplier | Y | [Refer to Gas Valid Suppliers](#gas) |
| electricitySupplier | Y | [Refer to Electricity Valid Suppliers](#elec) |
| businessName | Y | 100 Characters Max |
| businessAddress | Y | 255 Characters Max |
| fullName | Y | 120 Characters Max |
| email | N | 100 Characters Max |
| mobile | Y | 30 Characters Max |
| gasRenewalDate | N | 7 Characters Max format('MM-YYYY') |
| electricityRenewalDate | N | 7 Characters Max format('MM-YYYY') |
| gasSpend | N | 13 Characters Max |
| electricitySpend | N | 13 Characters Max |
| notes | N | 64kb Characters Max around 64000 characters depending on encoding|

#### Status Codes

**Response 201:** No response given

**Response 400:**

!!! Validation errors !!!

energyType:

```JSON
{
    "error": {
        "message": "Invalid Type of Energy",
        "body": "Has to be ‘Gas', ‘Electric’ or 'Both’"
    }
}
```

gasSupplier:

```JSON
{
    "error": {
        "message": "Invalid Gas supplier",
        "body": "Please check API docs"
    }
}
```

electricitySupplier:

```JSON
{
    "error": {
        "message": "Invalid Electric supplier",
        "body": "Please check API docs"
    }
}
```

businessName:

```JSON
{
    "error": {
        "message": "Invalid business name",
        "body": "Business name has to be 1 - 100 chars"
    }
}
```

street:

```JSON
{
    "error": {
        "message": "Invalid street",
        "body": "street has to be 1 - 255 chars"
    }
}
```

postcode:

```JSON
{
    "error": {
        "message": "Invalid Postcode",
        "body": "please provide a valid postcode"
    }
}
```

city:

```JSON
{
    "error": {
        "message": "Invalid city",
        "body": "City has to be 1 - 255 chars"
    }
}
```

fullname:

```JSON
{
    "error": {
        "message": "Invalid Full name",
        "body": "Full name has to be 1 - 120 chars"
    }
}
```

email:

```JSON
{
    "error": {
        "message": "Invalid Email",
        "body": "Must be a valid email regex: TBC"
    }
}
```

mobile:

```JSON
{
    "error": {
        "message": "Invalid Mobile number",
        "body": "Must be a valid mobile phone number regex: TBC"
    }
}
```

gasRenewalDate:

```JSON
{
    "error": {
        "message": "Invalid Gas Renewal Date",
        "body": "Gas Renewal Date format MM-YYYY"
    }
}
```

electricityRenewalDate:

```JSON
{
    "error": {
        "message": "Invalid Electricity Renewal Date",
        "body": "Electricity Renewal Date format incorrect  MM-YYYY"
    }
}
```

gasSpend:

```JSON
{
    "error": {
        "message": "Invalid Gas Spend",
        "body": "Gas Spend has must be a decimal 1.00"
    }
}
```

electricitySpend

```JSON
{
    "error": {
        "message": "Invalid Electricity Spend",
        "body": "Electricity Spend has must be a decimal 1.00"
    }
}
```

**Response 403:**

```JSON
{
  "error": "INVALID Token",
  "message": "Please check you are using the correct token",
}
```

**Response 404:**

```JSON
{
  "error": "URL Not Found"
}
```

**Response 405:**

```JSON
{
  "error": "Method Not Allowed",
  "message": "This endpoint only supports POST method requests",
}
```

**Response 500:**

```JSON
{
  "error": "Internal server error"
}
```
