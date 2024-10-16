# InputRules - Input Rules Library 

Is an Alpha version, develop in progress, do not use it in production

---

Predefined rules for processing data input (Forms/JSON/HTTP Requests)

## Example
```python
from inputrules import InputRules

#JSON Example
data = {
        "id":100,
        "data": {
            "name":"  Alvaro ",
            "lastname":" De Leon  ",
            "age":35,
            "email": "asdasd",
            "opt":"30",
            "parms":[
                10,20,30,40,50,60,70,80,90,100
            ],
            "phones": {
                "name":"Zaraza",
                "home":"123456",
                "cell":"123456"
            }
        }
    }
#Example of list of options
options = ['10','20','30','40','50']

o = InputRules(data)

o.rules("id","required,integer")
o.rules("data.name","required,string","trim,upper")
o.rules("data.lastname","required,string","trim,lower")
o.rules("data.age","required,integer")
o.rules("data.phone","string")
o.rules("data.email","string","b64encode")
o.rules("data.opt","options",options=options)
o.rules("data.phones.name","required,string")

if o.verify():
    print("Data is valid")
    data = o.data()
    print(data)
```

## Rules
Name|Description|Example
---|---|---

## Filters
Name|Description|Example
---|---|---