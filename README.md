# Marketing External API

## Links

[Create Lead](#create-lead)

## <a name="create-lead"></a>Create Lead

**Method: GET**

**Test-URL:** staging.greenpoweradvice.com/api/marketing

**Live-URL:** www.greenpoweradvice.com/api/marketing

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
  "Crown&#x20;Gas&#x20;&amp;&#x20;Power",
  "GDF&#x20;Suez",
  "BES",
  "Axis",
  "British&#x20;Gas&#x20;Business",
  "CNG",
  "Corona&#x20;Energy",
  "Dong&#x20;Energy&#x2f;Orsted",
  "E.ON",
  "Ecotricity",
  "EDF",
  "Enterprise&#x20;Gas",
  "Extra&#x20;Energy",
  "First&#x20;Utility",
  "Gazprom&#x20;Energy",
  "Good&#x20;Energy",
  "Haven&#x20;Power",
  "Hudson&#x20;Energy",
  "LoCO2&#x20;Energy",
  "N-Power",
  "Opus&#x20;Energy",
  "Ovo&#x20;Energy",
  "Regent&#x20;Gas",
  "Scottish&#x20;Power",
  "SmartestEnergy",
  "SSE",
  "Total&#x20;Gas&#x20;&amp;&#x20;Power",
  "United&#x20;Gas&#x20;&amp;&#x20;Power",
  "WINGAS",
  "Yorkshire&#x20;Gas&#x20;&amp;&#x20;Power",
  "Yu&#x20;Energy",
  "Utility&#x20;Warehouse",
  "BG&#x20;Corp.",
  "BG&#x20;SME",
  "Scottish&#x20;Gas",
  "One&#x20;Energy",
  "NEPO",
  "Economy&#x20;Gas&#x20;Ltd",
  "D-Energi",
  "ME&#x20;Energy",
  "The&#x20;Gas&#x20;Company",
  "Utilita",
  "Prime&#x20;Gas&#x20;and&#x20;Power",
  "Solarplicity",
  "PFP&#x20;Energy",
  "Valda&#x20;Energy",
];
```

**<a name="elec"></a>elec**

```JSON
[
  "-None-",
  "Axis",
  "BES",
  "BG&#x20;Corp",
  "BG&#x20;SME",
  "British&#x20;Gas&#x20;Business",
  "CNG",
  "Corona&#x20;Energy",
  "Crown&#x20;Gas&#x20;&amp;&#x20;Power",
  "Dong&#x20;Energy&#x2f;Orsted",
  "Dual",
  "E.ON",
  "Ecotricity",
  "EDF",
  "Enterprise&#x20;Gas",
  "Extra&#x20;Energy",
  "First&#x20;Utility",
  "Gazprom&#x20;Energy",
  "GDF&#x20;Suez",
  "Good&#x20;Energy",
  "Haven&#x20;Power",
  "Hudson&#x20;Energy",
  "LoCO2&#x20;Energy",
  "N-Power",
  "Opus&#x20;Energy",
  "Ovo&#x20;Energy",
  "Regent&#x20;Gas",
  "Scottish&#x20;Power",
  "SmartestEnergy",
  "SSE",
  "Total&#x20;Gas&#x20;&amp;&#x20;Power",
  "United&#x20;Gas&#x20;&amp;&#x20;Power",
  "Utility&#x20;Warehouse",
  "WINGAS",
  "Yorkshire&#x20;Gas&#x20;&amp;&#x20;Power",
  "Yu&#x20;Energy",
  "One&#x20;Energy",
  "NEPO",
  "D-Energi",
  "Unicom",
  "The&#x20;Gas&#x20;Company",
  "Utilita",
  "Western&#x20;Power",
  "F&amp;S&#x20;Energy",
  "Npower&#x20;Corp.",
  "Prime&#x20;Gas&#x20;and&#x20;Power",
  "Solarplicity",
  "PFP&#x20;Energy",
  "Valda&#x20;Energy",
  "Bryt&#x20;Energy",
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
