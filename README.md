# Marketing External API

## Links

[Create Lead](#create-lead)

## <a name="create-lead"></a>Create Lead

**Method: GET**

**Test-URL:** staging.trufl.com/api/marketing
**Live-URL:** www.trufl.com/api/marketing

**Prefix:** /tfli/lead

**Params:**

```JSON
N/A
```

**Query Params:**

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

#### Status Codes

**Response 201:** No response given

**Response 400:**

```JSON
{
  "message": "Missing UUID"
}
```

**Response 403:**

```JSON
{
  "message": "Unauthorised User"
}
```

**Response 500:**

```JSON
{
  "message": "Internal Server Error"
}
```
