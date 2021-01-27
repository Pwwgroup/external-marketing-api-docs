# Marketing External API

## Links

[Create Lead](#create-lead)

## <a name="create-lead"></a>Create Lead

**Method: GET**

**Test-URL:** https://staging.greenpoweradvice.co.uk/api/marketing

**Live-URL:** https://www.greenpoweradvice.co.uk/api/marketing

**URL Prefix:** /tfli/lead

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

**Body**

```JSON
{
  "businessOwner": "Y",
  "energyType": "both",
  "gasSupplier": "British Gas",
  "electricitySupplier": "British Gas",
  "businessName": "Utility Locker",
  "businessAddress": "18 School Ln, Liverpool L1 3BT",
  "fullName": "Thomas Dittmer",
  "email": "test@test.com",
  "mobile": "07981231234"
}
```

#### FullName rules

We only support

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
| businessOwner | N | 1 Characters Max |
| energyType | N | ('electricity', 'gas', 'both') |
| gasSupplier | Y | [Refer to Gas Valid Suppliers](#gas) |
| electricitySupplier | Y | [Refer to Electricity Valid Suppliers](#elec) |
| businessName | Y | 100 Characters Max |
| businessAddress | N | 255 Characters Max |
| fullName | Y | 120 Characters Max |
| email | Y | 100 Characters Max |
| mobile | Y | 30 Characters Max |

#### Status Codes

**Response 201:** No response given

**Response 400:**

!!! Validation errors !!!

```JSON
{
  "error": [
      "Invalid gas Supplier",
      "Invalid Electricity Supplier",
      "Invalid Business Name",
      "Business Name greater than 100 characters",
      "Invalid email address",
      "Email address greater than 100 characters",
      "Invalid Full name",
      "Full name is greater than 120 characters",
      "Invalid mobile number",
      "mobile number greater than 30 characters"
  ]
}
```

```JSON
{
    "error": {
        "message": "Invalid Mobile number",
        "body": "Must be a valid mobile phone number regex: TBC"
    }
}
```

```JSON
{
    "error": {
        "message": "Invalid Email",
        "body": "Must be a valid email regex: TBC"
    }
}
```

```JSON
{
    "error": {
        "message": "Invalid Full name",
        "body": "Full name has to be 1 - 120 chars"
    }
}
```

```JSON
{
    "error": {
        "message": "Invalid business name",
        "body": "Business name has to be 1 - 100 chars"
    }
}
```

```JSON
{
    "error": {
        "message": "Invalid Electric supplier",
        "body": "Please check API docs"
    }
}
```

```JSON
{
    "error": {
        "message": "Invalid Gas supplier",
        "body": "Please check API docs"
    }
}
```

```JSON
{
    "error": {
        "message": "Invalid Type of Energy",
        "body": "Has to be ‘Gas', ‘Electric’ or 'Both’"
    }
}
```

```JSON
{
    "error": {
        "message": "Invalid Business Owner",
        "body": "Has to be ‘Y' or 'N’"
    }
}
```

```JSON
{
    "error": {
        "message": "Invalid business address",
        "body": "Business name has to be 1 - 255 chars"
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
