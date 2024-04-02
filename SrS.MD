# 2.General description

## 2.1 Product perspective

### 2.1.1 System interface
```mermaid
block-beta
  User space:1 Server_web
  User --> Server_web
  Server_web --> User 
  Server_web space:1 DB[("DB")]
  Server_web --> DB
  DB --> Server_web
```

### 2.1.2 User interface
The user can access the information(rental price,taxes,size,...) using a Site web.

### 2.1.3 Hardware interface
[*No hardware needed*]

### 2.1.4 Software interface
*Example of API JSON response*

``` json
{
  "codice": "MO+40-70",
  "utilizzo": "Agricolo",
  "lato": 32.04,
  "proprietario": "RSSMRA75A01F205Z"
}
```

### 2.1.5 Communication interface
These are the main protocols uses:

*REQUEST*
```mermaid
block-beta
  columns 6
  User space:3 Server_web
  User --"HTTPS[GET-request]"--> Server_web
  Server_web space:1 DB[("DB")]
  Server_web -- "Mongo query"--> DB
```

*RESPONSE*
```mermaid
block-beta
  columns 6
  User space:3 Server_web
  Server_web <--"JSON"--> User
  Server_web space:1 DB[("DB")]
  DB -- "Mongo response"--> Server_web
```

### 2.1.6 Memory requirements
[*No memory requirements*]

## 2.2 Product functions
The product has *4* main functions:

### 1. Area calculator

```mermaid
block-beta
  Input space:4 Function1
  Input -- "Sizes (side,radius,...)" -->
  Function1 space:2 Output
  Function1 -- "Area" --> Output
```

### 2. Property tax calculator

```mermaid
block-beta
  Input space:4 Function2
  Input -- "sizes , tax" --> 
  Function2 space:2 Output
  Function2 -- "Property taxes(€)" --> Output
```

### 3. Rental price calculator

```mermaid
block-beta
  Input space:4 Function3
  Input -- "sizes , tax , rental time" --> 
  Function3 space:2 Output
  Function3 -- "Rental prices(€)" --> Output
```

### 4. Property value

```mermaid
block-beta
  Input space:4 Function4
  Input -- "sizes , tax , benefits , location" --> 
  Function4 space:2 Output
  Function4 -- "Property taxes(€)" --> Output
```


## 2.3 User characteristics

The system interface will allow any non-specialized person to use the software.  
It is only required *1hour* beginner-course at the following link [Beginner tutorial](https://fake_link).

