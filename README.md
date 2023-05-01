# ChatGPT x Resume

### What is this?

This repo contains a collection of ChatGPT prompts to help you write or revise your resume. 
It also has prompts to help you generate a cover letter for a specific job post.

I developed these while revising the resumes of a few brave voulenteers.

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

I also asked ChatGPT what makes a good resume and you can see what it thinks in [What makes a good resume?](01-good-resume.md).

**Template**

I experimented with using the free Google Docs resume templates but layouts were very brittle. Inserting text that was a 
bit longer than the sample would cause the whole layout to break. Next, I tried looking for open source HTML templates and found [html-resume](https://github.com/BeyondCodeBootcamp/html-resume), 
but it is also very brittle.

I ended up building my own Bootstrap 5 template available in [template.html](template.html). 
It's a two column layout that's using Google Fonts to load Karla (Sans Serif) and Merriweather (Serif) fonts.
You can see what a PDF version looks like at [Patrick-Bateman.pdf](Patrick-Bateman.pdf). The PDF was created by
using Chrome's standard "Print to PDF" functionality.

The color palette in the template was generated by ChatGPT with this prompt:

**Prompt:**

> I'm building an HTML resume template, can you give me a 3 hex colors for a color palette?

**Reply:**
> Sure, here are three hex color codes that could work well together for an HTML resume template:
> 1. #2C3E50 - This is a deep blue color that could work well for headers or accent elements.
> 2. #F5B041 - This is a warm orange color that could be used for call-to-action buttons or other attention-grabbing elements.
> 3. #ECF0F1 - This is a light gray color that could be used for the background or as a secondary color for text or other elements.


Any resume template should work for this though.

**Professional Statement**

Starting from the top of the resume, the first thing to build out is the "Professional Statement".

What I did was come up with 3 unique attributes about the candidate and then feed those through this prompt.

The facts I included in the prompt are items that make the candidate unique.
For example:
* That they had started and operated a business
* Experience with a unique tool like MakerBot
* A unique certification

**Prompt:**
> You are an elite career coach helping a candidate develop their resume.
> Write a powerful, concise professional statement for the candidate.
> Incorporate these facts:
> [[ List of facts ]]

I did have to ask ChatGPT to refine the statement 1-2 times to get it to flow correctly.

**Education**

Listing the institutions that you attended is straightforward and ChatGPT won't be helpful with that. 
Where ChatGPT can help is doing things like understanding what courses/certifications you should list on your resume and why.
And rewriting blocks of text with specific goals in mind.

**Coursework**

> You are an elite career coach helping a candidate develop their resume.
> The candidate has completed dozens of classes as part of a four-year degree.
> List these college courses in the order of importance of listing them in the resume. Provide a justification for each one.
> The candidate is optimizing to pass automated ATS filters and to highlight their unique value
> 
> [[ list of courses ]]

**Project descriptions:**

> Rewrite this project description to give an interviewer openings to ask questions about the project
> 
> [[ original description ]]

**Work**

Describing your past jobs is where ChatGPT is really going to excel. 
You should be able to use it to rewrite existing bullet points to be more compelling or satisfy specific requirements.
And maybe more interestingly, you could also customize the descriptions to the jobs you're applying for.

You can also feed ChatGPT a job title along with some details about the company and it'll generate generic 
but impressive sounding bullets for your job duties.

Here are some of the prompts I used:

**Prompt:**
> You are an elite career coach helping a candidate develop their resume.
> This is a description of the candidates job duties. Rewrite this job description to make it more appealing to an interviewer. Make it 3 bullet points.
>
> Description:
>
> [[ job description ]]

**Prompt:**
> You are an elite career coach helping a candidate develop their resume. 
> Generate a three bullet points description for a "Legal Executive Assistant" for a single attorney law firm

**Sidebar**

The template from above includes a right sidebar where you can list out things like certifications, relevant coursework, or software experience.
Personally, I think it looks bad if you list every course you've ever taken or every software tool you've used. 
Since it implies that you probably only have a passing familiarity with each of them.

Here's some of the prompts I used to identify important attributes:

**Prompt:**
> You are an elite career coach helping a candidate develop their resume.
> List these skills in the order of importance of listing them in the resume. Provide a justification for each one.
> The candidate is optimizing to pass automated ATS filters and to highlight their unique value
> [[ list of skills ]]

**Equipment**

**Prompt:**
> You are an elite career coach helping a candidate develop their resume.
> The candidate has experience with several pieces of equipment.
> List these pieces of equipment in the order of importance of listing them in the resume. Provide a justification for each one.
> The candidate is optimizing to pass automated ATS filters and to highlight their unique value
> [[ list of equipment ]]

**Software**

**Prompt:**
> You are an elite career coach helping a candidate develop their resume.
> The candidate has experience with several software tools.
> List these software tools in the order of importance of listing them in the resume. Provide a justification for each one.
> The candidate is optimizing to pass automated ATS filters and to highlight their unique value
> [[ list of software ]]

**Bonus: Cover Letter**

OK you have a kick ass resume but now you need a cover letter... ChatGPT can help you with that. 

I created a prompt where I fed in the full text of the candidate resume along with a job description and asked ChatGPT
to figure out what attributes about the candidate to highlight in the cover letter:

**Prompt:**

> You are an elite career coach helping a candidate write a cover letter for a specific job.
> Review the resume and job description to find 3 relevant items from the resume to mention in the cover letter.
>
> If none exist, reply with "None"
>
> Resume:
>
> [[ paste resume text ]]
>
> Job Description:
>
> [[ paste job description text ]]

Then, I fed those into a second prompt to generate the cover letter

**Prompt:**
> You are an elite career coach helping a candidate write a cover letter for a specific job.
> Write a 200 word cover letter applying for the job described below.
> Incorporate the attributes about the candidate that make them a good fit for the job.
>
> Attributes:
>
> [[ result of the previous prompt ]]
>
> Job Description:
> [[ paste job description text ]]

**Bonus: Entity extraction**

As a software engineer, a natural follow up question is "OK cool, can we automate it?"

For the "revise a resume" use case, the first step would be taking an existing resume 
and extracting the key details out  of it in a structured fashion. 
Dumping the text out of a PDF or DOCX file is straightforward but what about the entity extraction?

Normal NLP methods are OK for this task but you'll typically only be able to extract high level facts, not the details.
For example, from the [sample resume](Patrick-Bateman.pdf) 
you'd be able to extract that they listed "Axe Capital" and "Rebel Partners" as employers but you won't be able to extract the
bullet point job descriptions.

Can ChatGPT do better? At least from my quick tests, absolutely.

See [Extractors](02-extractors.md) for the prompts I used to try extracting data as JSON from the resumes.

### OK, but...

As of writing (May 2023), using ChatGPT to give yourself a leg up on your resume or cover letter is a "strong recommend".
But that may change quickly as ATS systems begin to flag AI generated resumes and hiring managers start realizing they're seeing
the same AI generated content across dozens of resumes.

But as Mom always said: Don't hate the player, hate the game.
