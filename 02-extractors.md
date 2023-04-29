## Extract entities from resume text

Extract plain text from a PDF with [pdftotext](https://www.xpdfreader.com/pdftotext-man.html):

```
$ pdftotext resume.pdf -
```



**Extract candidate name**

**Prompt:**

> You are an AI being used inside an applicant tracking system. 
> You are parsing resume text to extract the requested field. 
> 
> From this resume text, extract the candidate's name as JSON. Reply with only that JSON and no other text.
> 
> [[ RESUME TEXT ]]

**Reply:**
> {"name": "Patrick Bateman"}


**Prompt:**
> You are an AI being used inside an applicant tracking system.
> You are parsing resume text to extract the requested field.
>
> Extract all the available contact information as a list of JSON. Reply with only that JSON and no other text. 
> 
> For example: [{"type": "email", "value": "patrick.bateman@gmail.com"}]

**Reply:**
```json
[
   {
      "type":"phone",
      "value":"555-345-2345"
   },
   {
      "type":"email",
      "value":"patrick.bateman@gmail.com"
   },
   {
      "type":"linkedin",
      "value":"linkedin.com/in/patrick-bateman/"
   }
]
```

