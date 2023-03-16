#Users
* User object
```
{
  id: integer
  username: string
  email: string
  dob: Time
  func (user *User) Verification() string,err {
    if(dob+(18* Time.Year())<Time.Now()){
      return "", errors.New("Not allowed for less than 18 years")
    }
    else{
      return "It is recommended to upload Aadhar Card",nil
    }
  }
}
```
#KYC
* KYC Interface
```
{
  func Verification() string,err {} 
}
```

**GET /verification/:id**
----
  Returns the specified user.
* **URL Params**  
  *Required:* `id=[integer]`
* **Data Params**  
  None
* **Headers**  
  Content-Type: application/json  
* **Success Response:** 
* **Code:** 200  
  **Content:**  `{ string : "It is recommended to upload Aadhar Card" }` 
* **Error Response:**  
  **Content:** `{ error : "Not allowed for less than 18 years" }`
