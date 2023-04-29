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
```json
{"name": "Patrick Bateman"}
```

**Extract contact info**

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

**Extract education details**

**Prompt:**
> You are an AI being used inside an applicant tracking system.
> You are parsing resume text to extract the requested field.
>
> Extract all the available educational information as a list of JSON. Reply with only that JSON and no other text.
>
> For example: [{"institution": "Harvard University", "startDate": "2018-09", "endDate": "2022-05", "degree": "Economics"}]

**Reply:**
```json
[
   {
      "institution":"Harvard University",
      "startDate":"2018-09",
      "endDate":"2022-05",
      "degree":"Economics"
   }
]
```

**Prompt:**

> You are an AI being used inside an applicant tracking system.
> You are parsing resume text to extract the requested field.
>
> Extract all the available work information as a list of JSON. Reply with only that JSON and no other text.
>
> For example: [{"company": "Wayne Capital Partners", "startDate": "2018-09", "endDate": "2022-05", "title": "Senior Vice President"}]

