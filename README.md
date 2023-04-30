# ChatGPT x Resume

### What is this?

This repo contains a collection of ChatGPT prompts to help you write or revise your resume. 
It also has prompts to help you generate a cover letter for a specific job post.

### Should you use this?

Probably not. Definitely not without reviewing the ChatGPT output.

I (Ashish) have no qualifications or relevant experience that would make me particularly good at writing or reading resumes.
So use at your own risk.

### I want to live dangerously, let's do this

Love the sense of adventure!

The overall thinking is that:

* A "technically well written" resume, one that's free of spelling errors and written clearly, will be well received by hiring managers
* When candidates apply for a job, their resumes are often reviewed by automated systems that are looking for specific keywords
* ChatGPT isn't good at writing interesting prose, but it is good at writing "technically correct" paragraphs that include specific elements
* So we should be able to use ChatGPT to write the text for a strong resume

**Template**

I experimented with using the free Google Docs resume templates but layouts were very brittle. Inserting text that was a 
bit longer than the sample would cause the whole layout to break. Next, I tried looking for open source HTML templates and found [html-resume](https://github.com/BeyondCodeBootcamp/html-resume), 
but it is also very brittle.

I ended up building my own Bootstrap 5 template available in [template.html](template.html). 
It's a two column layout that's using Google Fonts to load Karla (Sans Serif) and Merriweather (Serif) fonts.
You can see what a PDF version looks like at [Patrick-Bateman.pdf](Patrick-Bateman.pdf). The PDF was created by
using Chrome's standard "Print to PDF" functionality.

## Sections:

* [What makes a good resume?](01-good-resume.md)
* [Extract entities from resume text](02-extractors.md)
* [Professional statement](03-professional-statement.md)
* [Skills, Equipment, and Software](04-skills.md)
* [Education](05-education.md)
* [Work](06-work.md) 
* [Cover letters](07-cover-letter.md)