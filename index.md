## Table of contents

* [Overview](#overview)
* [Approach](#approach)
* [User Guide](#user-guide)
* [Developer Guide](#developer-guide)
* [Example Enhancements](#example-enhancements)
* [Team](#team)
* [Team Contract](#team-contract)
* [Milestone](#milestone)
* [Milestone 1 Progress](#milestone-1-screenshots-of-progress)
* [Milestone 2 Progress](#milestone-2-screenshots-of-progress)
* [Milestone 3 Progress](#milestone-3-screenshots-of-progress)
* [Deployment](#deployment)
* [Review and Feedbacks](#review-and-feedbacks)

## Overview

The Corponector web application provides a new way for local and non-local companies who want to recruit students from UH to make their (potential) opportunities known to students. At the same time, students can create profiles on the site with their interests. The site can match students to employers and vice-versa.

* [GitHub Organization](https://github.com/corponector) of Corponector containing all its repositories.

Technologies we plan on using for "Corponector":

* [React](https://reactjs.org/) for component-based UI implementation and routing.
* [Nextjs](https://nextjs.org/) to enhance the development process, particularly for full-stack applications. It adds additional tools for server-side rendering (SSR), static site generation (SSG), API routes, and more.
* [PostgreSQL](https://postgresql.org/) to handle structured data with well-defined schemas and relationships between entities.

* ![ci-badge](https://github.com/corponector/sourceCode/workflows/ci-corponector/badge.svg)


### Project Goals

The primary goals of this project are to:
- **Enhance Job and Internship Visibility**: Make it easy for students to explore a wide range of opportunities from numerous companies.
- **Streamline Connections**: Allow companies to post details about potential positions and recruit students with the necessary skills and interests.
- **Match Skills and Interests**: Enable students to create profiles with their skills and career preferences, while companies can specify the skills they look for in candidates.
- **Support Admin Oversight**: Provide administrators with the ability to monitor site content, add new skill or location categories, and manage the platform.

## Approach

### Features

The **Corponector** application will deliver the following key features:

- **Company Profiles**: Companies can showcase their mission, location, recruiting needs, job descriptions, and relevant links. This enables students to understand the company's focus and the roles available.
  
- **Student Profiles**: Students can create profiles highlighting their skills, geographic preferences, and portfolio links, providing employers with a quick snapshot of their qualifications.
  
- **Matchmaking Capabilities**: The system will allow companies and students to be matched based on mutual interests, skills, and locations, helping students find opportunities that align with their career goals.

- **Admin Portal**: Administrators can monitor content, create new skill and location categories, and ensure a safe and professional platform environment.

### System Overview

The **Corponector** system will be built to serve three primary user roles:

- **Students**: Students can browse company profiles, set up their own profiles, and connect with companies based on their skills and location preferences.
- **Companies**: Companies can create profiles to post potential opportunities and manage recruitment needs for UH students.
- **Administrators**: Admins can oversee the platform, moderate content, and manage platform categories and settings.

After logging in, users will have access to personalized home pages where they can explore matches, set up their profiles, and navigate the platform based on their role.

## User guide

Here are some mockup designs to illustrate the planned structure and user experience of the **Corponector** platform. Our latest progress can be found in the <a href="#milestone-3-screenshots-of-progress">Milestone 3 Progress</a>.

Currently, companies and students are able to sign up where they will be prompted to enter in an email and password (the sign up page). After indicating if they are a student or company, the application will take them to a form to fill out more information about their profile (Student/Company Form). After finishing up the sign in process, they will be redirected to their profile pages.

On their profile pages, students will have a list of recommended companies while companies will have a list of recommened students. The information they have entered during the sign up process will also be displayed on the left side. Users will have an "Edit" button to change any of the information they have entered before, be it adding available positions to the company or changing skills the company is looking for or skills the student possesses.

In addition to the recommended students and companies listed on their profile page, there is also a "Search" page which lists all the users on the Corponector app, including students and companies. Users are able to sort by students or company only and by location or skills. If they are looking for a specific student or company, they are also able to type in what/who they are searching for.

### Landing Page

On the **Landing Page**, users can easily sign in or register by clicking the  **"Log In"** or **"Sign Up"** buttons located at the top right corner. New users can register by providing basic information such as their name, email, and role (student or company), while returning users can simply enter their credentials to access their personalized dashboard and start browsing opportunities or managing job postings.

<img src="images/landing-page.png" />

### Student Home/Profile Page

The **Student Home Page** displays job opportunities tailored to a student's skills, interests, and preferred locations, allowing them to browse and apply for internships and positions. Students can update their profiles to showcase their qualifications and increase their chances of matching with potential employers.

It also allows students to showcase their skills, interests, and professional experience, including a link to their portfolio. It provides a personalized view of their qualifications, making it easier for companies to find and connect with them for relevant job opportunities.

<img src="images/student-profile.png" />

### Company Home/Profile Page

The **Company Home Page** allows companies to manage their job postings and view candidates who match their required skills and location preferences. Companies can send messages to potential hires, update job listings, and track engagement with student profiles to find the best talent for their positions.

It showcases the company’s details, including an overview, location, job postings, and key contact information. Companies can update their profile, manage available positions, and track engagement with student applicants to attract the right talent.

<img src="images/company-page.png" />

### Admin Home Page

The **Admin Home Page** provides a centralized dashboard for managing job postings, user accounts, and ensuring content moderation across the platform. Admins can generate analytics and reports, manage categories and settings, and monitor site activity to maintain a smooth and organized user experience.

<img src="images/admin-page.png" />

### Browse Companies and Users

The **Browse Companies and Users** page allows students and employers to filter and search for companies and candidates based on specific criteria such as skills, geographic location, and job type. This feature helps users easily find matches that align with their professional interests or hiring needs.

<img src="images/browse-page.png" /> 

## Developer Guide

Here is our guide for developers to help with the process of downloading, installing, running, and modifying the system.

### Download

You should **Download** VSCode or any source code editor with a built-in terminal. Download 
PgAdmin or any platform that manages PostgreSQL. 

### Install And Run

To **Install** our source code, you must first clone the repository to your system using your preferred source-code editor. Then in the terminal, cd into the source code and install third-party libraries by running 'npm install'


<img src="images/clone.png" /> 

To create Database
1. Open a Terminal window in VSCode and run the command 'createdb -U User Corponector'. 
   This will create your Database
2. Copy the 'sample.env' file to a new file called '.env'.
3. Edit the .env file to set the DATABASE_URL to
   postgresql://username:password@localhost:5432/Corponector?schema=public.
4. Migrate the database by running the command 'npx prisma migrate dev'. This will create the tables in the Corponector database.
5. Seed the database by running the command 'npx prisma db seed'. This will populate the tables with some sample data.
6. Start Next.js using 'npm run dev', and check "http://localhost:3000" (and the console) to ensure that the new landing page displays correctly.

### Modify
To **Modify**, use your preferred code editor, in our case VsCode. Client-side code files are stored in the src/component folder. They handle user interactions like clicks and form submissions. The server side will be in the src/app folders. Server-side code processes requests, interacts with databases, and generates HTML to send to the client.

## Example Enhancements

* Notifications via email and/or SMS.

## Team
* [Amy Shin](https://tlsdbfla00.github.io/)
* [Alexis Karl Buted](https://abuted.github.io/)
* [Alessandra Gudoy](https://alessandra-gudoy.github.io/)
* [Blake Ilagan](https://byilagan808.github.io/Professional-Portfolio-/)
* [Justine Ponce](https://justonepg.github.io/JustinePonce.github.io/)

## Team Contract
<a href="https://docs.google.com/document/d/1MjatDBetUF2S13ewZnPrmrwbtz-P3T6gPSgwcZZgUh4/edit?usp=sharing">
  <img src="images/United_States_Declaration_of_Independence.jpg">
</a>

## Milestone
* [Milestone 1](https://github.com/orgs/corponector/projects/1/views/1)
* [Milestone 2](https://github.com/orgs/corponector/projects/3)
* [Milestone 3](https://github.com/orgs/corponector/projects/6)

## Milestone 1: Screenshots of Progress
Landing Page:
<img src="images/landing-progress.png" alt="landing page"/>

Sign In Page:
<img src="images/signin-progress.png" alt="sign in page"/>

Sign Up Page:
<img src="images/signup-progress.png" alt="sign up page"/>

If registering a student profile:
<img src="images/student-prof-form-progress.png" alt="student profile form page"/>

If registering a company profile:
<img src="images/company-form-progress.png" alt="company profile form page"/>

Student Profile Page:
<img src="images/student-profile-progress.png" alt="student profile page"/>

Search Page:
<img src="images/browsehomepage.png" />

Company Home Page:
<img src="images/company-page-progress1.png"/>
<img src="images/company-page-progress2.png"/>

Admin Dashboard:
<img src="images/admin-dashboard.png" />
<img src="images/admin-two.png" />
<img src="images/admin-three.png" />
<img src="images/admin-four.png" />
<img src="images/admin-five.png" />

## Milestone 2: Screenshots of Progress

Landing Page:
<img src="images/new-landing.png" />
<img src="images/new-landing2.png" />
Learn more about our goal and a link to the sign-up page. The navigation bar includes our Homepage, Search page, and email.

Add Company Page:
<img src="images/new-addcompanypage.png" />
<img src="images/company11.png" />
<img src="images/company22.png" />
Add Company information to our database and can create as many positions you want.

Student Profile Page:
<img src="images/student-page-milestone2.png"/>
Profile for the current student user, displaying their skills and recommended companies. Also a link to the edit student page. It reads from our database.

Edit Student Profile Page:
<img src="images/edit-student.png"/>
Edits student information

Search Page:
<img src="images/new-searchpage-1.png" />
<img src="images/new-searchpage-2.png" />
Can search student and company names. Can filter out Students or Companies. Can use tags to only include students and companies with specific skills, locations, and positions. Student Card shows their name, picture, skills, and a link. Company Card shows their name, overview, email, links, and positions which include the title, description, skills, number of hires, and salary range. It reads from our database.

## Milestone 3: Screenshots of Progress
Landing Page:
<img src="images/M3Landingpage-1.png" />
<img src="images/M3landingpage-2.png" />
* Includes information about our goals
* Link to our sign-up page

Search Page:
<img src="images/M3Searchpage-1.png" />
<img src="images/M3searchpage-2.png" />
* Filter Students and Company
* Tags include Location, Skills, and Positions
* Includes Student and Company Cards with basic information
* Clicking Cards will go to their profile
* Search by Student or Company name

Student Profile:
<img src="images/M3studentprofile.png" />
* Includes the student's basic information

Student Page:
<img src="images/M3Currentstudentprofile.png" />

* Include student basic information
* User Student profile
* Include Company Card for recommended Companies
* Link to the edit page

Edit Student Page:
<img src="images/M3editcurrentstudentprofile.png" />
* Edit student information

Company Profile:
<img src="images/M3companyprofile.png" />
* Include company basic information
* Include Open positions for the company

Company Page:
<img src="images/M3currentcompanyprofile-1.png" />
<img src="images/M3currentcompanyprofile-2.png" />
* Include company basic information
* User Company Profile
* Include Open positions for the company
* Include Student Card for recommended Students
* Link to edit page

Edit Company Page:
<img src="images/M3editcurrentcompanypage-1.png" />
<img src="images/M3editcurrentcompanyprofile-2.png" />
* Edit company basic information
* Edit, add, or remove positions

Admin Page:
<img src="images/M3Adminpage-1.png" />
<img src="images/M3Adminpage-2.png" />
* Change the Role of a user to Admin or Student or Company
* Can remove accounts
* Can remove Positions
* Includes the number of accounts and job positions

## Deployment
* [Vercel](https://corponector.vercel.app/)

## Review and Feedbacks

Summarizing the reviews, they found that the Corponector app is simple and straightforward to use. However, it was pointed out that there needs to be an indication that the app is loading. For example, when submitting the profile information for the student, the users don't know that the app takes a few seconds to submit the data to the database, therefore, the user presses the button twice causing the entry to be pushed to the database twice.

Additionally, they said that it is very useful in connecting students and companies. It was recommended that there should be more information about the students, such as GPA, and having a button to specify which company a student is interested in and show the companies which students are interested in the company.

* Oscar Tio
<img src="images/OscarFeedback.png"/>

* Rhea Mae Arellano
<img src="images/rhea-feedback.png"/>

* Mark Shin
<img src="images/MarkFeedback.jpg"/>

* Kaitlyn
<img src="images/feedback_k.png"/>

* Camilla Nguyen 
<img src="images/camFeedback.png"/>





