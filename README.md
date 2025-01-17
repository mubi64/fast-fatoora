<p align="center">
  <img align="center" src="https://github.com/NafieAlhilaly/fast-fatoora/blob/main/images/fast-fatoora-logo.png" width=300/>
</p>

---------

[![GitHub stars](https://img.shields.io/github/stars/NafieAlhilaly/api-fatoora?style=for-the-badge&logo=github)](https://github.com/NafieAlhilaly/api-fatoora/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/NafieAlhilaly/api-fatoora?style=for-the-badge&logo=github)](https://github.com/NafieAlhilaly/api-fatoora/network)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg?style=for-the-badge&logo=python)](https://github.com/psf/black)
[![GitHub license](https://img.shields.io/github/license/NafieAlhilaly/api-fatoora?style=for-the-badge&logo=github)](https://github.com/NafieAlhilaly/api-fatoora/blob/main/LICENSE)
[![ZATCA](https://img.shields.io/badge/ZATCA-Fatoora-green?style=for-the-badge)](https://zatca.gov.sa/ar/E-Invoicing/Introduction/Pages/What-is-e-invoicing.aspx)
[![FastAPI](https://img.shields.io/badge/FastAPI-%E2%9D%A4%EF%B8%8F-brightgreen?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![Heroku](https://img.shields.io/badge/Heroku-fast--fatoora-blue?style=for-the-badge&logo=heroku)](https://api-fatoora.herokuapp.com)

# fast-fatoora


You can try it with simple ui @ [Heroku](https://api-fatoora.herokuapp.com/)


fast-fatoora is an open API to help generating QR-code for [ZATCA's e-invoice known as "Fatoorah"](https://zatca.gov.sa/en/E-Invoicing/Introduction/Pages/What-is-e-invoicing.aspx) 




full API [documentations](https://api-fatoora.herokuapp.com/docs) 


---------
## how to use it 

lets say you have the following data 
```json
{
  "seller_name":"Nafie",
  "tax_number":"981293479834",
  "date":"2021-12-06 16:14:17.374909",
  "total_amount":"100.00",
  "tax_amount":"0.50"
}
```

### To base64
Use /to_base64 to get base64 encoded information
```
Parameter :
  seller_name: required
  tax_number: required
  date: optional, if not provided created date and time will be added
  total: required
  tax_amount: required
  
  
https://api-fatoora.herokuapp.com/to_base64?seller_name=Nafie&tax_number=981293479834&total=100.00&tax_amount=0.50&date=2021-12-06%2016%3A14%3A17.374909
```
[Try it](https://api-fatoora.herokuapp.com/to_base64?seller_name=Nafie&tax_number=981293479834&total=100.00&tax_amount=0.50&date=2021-12-06%2016%3A14%3A17.374909)

### To QR-Code image
Use /to_qrcode_image to generate QR-Code image
```
Parameter :
  seller_name: required
  tax_number: required
  date: optional, if not provided created date and time will be added
  total: required
  tax_amount: required
  
  

https://api-fatoora.herokuapp.com/to_qrcode_image?seller_name=Nafi&tax_number=981293479834&total=100.00&tax_amount=0.50&date=2021-12-06%2016%3A14%3A17.374909
```
[Try it](https://api-fatoora.herokuapp.com/to_qrcode_image?seller_name=Nafi&tax_number=981293479834&total=100.00&tax_amount=0.50&date=2021-12-06%2016%3A14%3A17.374909
)

### Full E-Invoice(fatoora)
Use /full_fatoora to get e-invoice with qrcode image
```
Parameter :
  fat_number: Optional, e-ivoice number/id if not ptovided it will be filled with random numbers
  seller_name: required
  tax_number: required
  date: optional, if not provided created date and time will be added
  total: required
  tax_amount: required
  
  

https://api-fatoora.herokuapp.com/full_fatoora?seller_name=Nafie&tax_number=981293479834&total=100.00&tax_amount=0.50&date=2021-12-06%2016%3A14%3A17.374909&fat_number=5837

```
[Try it](https://api-fatoora.herokuapp.com/full_fatoora?seller_name=Nafie&tax_number=981293479834&total=100.00&tax_amount=0.50&date=2021-12-06%2016%3A14%3A17.374909&fat_number=5837
)

# Devolepment
To start your local devolepment 
### clone repo
```bash
git clone https://github.com/NafieAlhilaly/fast-fatoora.git

```
```bash
cd fast-fatoora

```
### install dependencies
using pip:
```bash
pip install -r requirements.txt
```

using poetry(recommended):
```bash
poerty install
```

### run the local devolepment server
```bash
python app/main.py
```
server will run on https://127.0.0.1:8000
