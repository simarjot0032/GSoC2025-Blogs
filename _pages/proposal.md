---
layout: page
permalink: /proposal/
title: Proposal
---

# BRL-CAD OGV Migration

### GSoC Project proposal for BRL-CAD

### Personal Information

- **Name**: Simarjot Singh
- **Email**: [simarjot0032@gmail.com](mailto:simarjot0032@gmail.com)
- **Phone**: +91 985 566 2271
- **GitHub**: [simarjot0032 (Simarjot Singh) Github](https://github.com/simarjot0032)
- **LinkedIn**: [Simarjot Singh](https://www.linkedin.com/in/simarjot0032)
- **Blog**: [Simarjot Singh](https://simarjot0032.medium.com)

#### Brief Background Information

I am currently in the second year of my B.Tech in Computer Science and Engineering at Guru Nanak Dev Engineering College, India. I have experience in HTML, CSS, JS, SCSS, React with JS/TS, Next.js, React Native, Firebase, and Supabase. I am proficient with version control systems such as Git and GitHub. In addition, I have successfully completed several freelance projects, delivering professional and high-quality web solutions.

#### Projects

- I have contributed to the Sikh Youth Coding Initiative (SYCI) under the Khalis Foundation. I have developed an NPM package that converts speech to text (Punjabi language), which will be integrated into their apps.
  Link: [punjabi-voice-search - npm](https://www.npmjs.com/package/punjabi-voice-search)

- Recently, I contributed to the Khalis Foundation app, which is built with React Native.
- During my major project for my diploma, I developed a website for an architectural company to showcase their portfolio, and I integrated a management system into their website using Firebase.
- I have also developed another website for an architectural company based in Canada. It was a freelance project.
  Link: [Meikle Designs](https://www.meikledesigns.com/)
- I also developed a website for a car washing company in New Zealand.
  Link: [Divine Wash & Clean Limited](https://divineshine.co.nz/)
- I have also completed several projects for my practice and to enhance my skills. Recently, I started another project in Next js for managing passwords, inspired by [BitWarden](https://bitwarden.com/). This project is in the initial stages.
  <br>

### Project Information

####  Project Title: BRL-CAD OGV Migration

##### Project Length: 350h

#### Project Proposal Brief Summary

This project proposes a complete rewrite of BRL-CAD's existing OGV, which currently uses Meteor.js, an older framework no longer actively maintained. I suggest converting it to a more stable and maintainable framework. I plan to use Next.js, a modern React-based framework, for the frontend. SCSS/SASS will be used for styling, Nest.js will be used as the backend framework for better efficiency and type-safety, and Three.js will be used for modelling 3-D graphics on the web. Additionally, the frontend will be redesigned following industry-standard UI/UX best practices. Also, it will be made sure to use libraries that have LTS support and are correctly maintained.

#### Detailed Project Description

#### Current Scenario

1. Currently, the project has an old and outdated tech stack.
2. The UI/UX lags behind today’s designs.
3. Currently, it supports only .g files, limiting scalability and reliability.
4. The project requires a comprehensive redesign for better usability,
   scalability, and maintainability.

#### Task Details

1. **The design**
   **<u>Description</u>**: The current OGV platform’s interface is outdated and lacksconsistency with modern design standards, making it less intuitive for users.
   **<u>Proposed Solution</u>**: I will work on initial wireframes in Figma to conceptualize the overall layout and UI flow. These wireframes will serve as a starting point, evolving based on feedback and feature expansion. These wireframes will encompass key pages, including the landing page, model upload UI, conversion dashboard, and profile page layouts. The wireframes will include:
   - Conversion UI with drag-and-drop upload
   - Model repository dashboard
   - Model viewer integration
   - Explore/feed page with filters.
2. **Tech Stack**:
   **<u>Description</u>**: Selecting and configuring the right boilerplate (starter template + dev tooling) is a foundational task. A good boilerplate ensures that the project follows modern development standards, improves contributor experience, and avoids technical debt.
   **<u>Proposed Solution</u>**: Based on discussions and the project's needs, I will carefully select the optimal boilerplate setup. For frontend I will use **Next.js**, and for the backend, I will use **Nest.js** for better scalability. Once finialized, I will:
   - Set up a clean project structure
   - Integrate essential tooling:
     - **SCSS** for styling
     - **ESLint** + Prettier for code consistency
     - **Husky** + Commitlint for commit standard enforcement
     - **TypeScript**
     - Implement routing, fundamental pages, and reusable
       placeholder components to establish a scalable foundation.
3. **File Upload & Conversion System**
   **<u>Description</u>:** This is the foundation of the conversion service where users will be able to upload 3D model files (like .stl, .obj, .3dm, etc.) and have them automatically converted to polygonal formats using BRL-CAD’s gcv tool. The goal is to remove friction and allow smooth file transformation with minimal user interaction.
   **<u>Proposed Solution</u>:** I will implement a drag-and-drop file uploader using a React-based component (like react-dropzone). Once uploaded, files will be passed to the backend endpoints, leveraging a queue-based system to efficiently handle conversions using BRL-CAD's gcv tool.

4. **Download Options**
   **<u>Description</u>:** After the conversion process, users can download the converted files in a variety of formats depending on what the GCV tool supports
   **<u>Proposed Solution</u>:** The backend will generate downloadable versions of the converted files in commonly used formats (.g, .stl, .obj, etc.). Users can choose the desired format, and optionally download all results as a zipped archive. This will be integrated into the user dashboard for easy access.

5. **Conversion Progress & Notifications**
   **<u>Description</u>:** : Converting 3D files, especially large ones, can take time. Users should see real-time feedback on the progress to improve the experience.
   **<u>Proposed Solution</u>:** I will implement a progress bar in the UI (e.g., Queued, Converting, Done). For real-time updates, I will use WebSockets. If a file takes longer than expected, a notification system (in-app, toast alerts) will alert the user when the process is done.
6. **Multi-File Upload & Batch Conversion**
   **<u>Description</u>:** Allowing users to upload multiple files at once increases usability and efficiency, especially for professionals converting project bundles.
   **<u>Proposed Solution</u>:** I will enhance the uploader to accept multiple files. On the backend, process each file either concurrently (if resources allow) or via a queue-based system for sequential handling. Show progress for each file individually in the UI. On completion, allow batch download or per-file access.

7. **Mobile Responsive Design**
   **<u>Description</u>:** Modern users frequently access web services via mobile devices, so the interface must be responsive and optimized for smaller screens.
   **<u>Proposed Solution</u>:** I will use a responsive layout (e.g., CSS Flexbox/Grid and media queries) to ensure the conversion service works on tablets and smartphones. I will test the interactions like file upload, progress tracking, and download actions for mobile-friendliness. I will also use SCSS for better scalability.

8. **User Authentication & Profiles**
   **<u>Description</u>:** Users need to create profiles to manage and share models.
   Profiles also enable social features like following and discovery.
   **<u>Proposed Solution</u>:** I will integrate OAuth providers (Google, GitHub) and email and password login. Users can edit their profile info (bio, picture, display name) and follow and unfollow others. The backend handles session management and secure tokens like JWT.

9. **Social Interaction Features**
   **<u>Description</u>:** To build a community, users should be able to interact with each other's models via likes, comments, and shares.
   **<u>Proposed Solution</u>:** I will implement like and comment systems with backend APIs and frontend counters. It will also display the view count to indicate the popularity. Users will receive notifications to keep them informed about activity related to their models. I will implement the abuse and spam detection and rate limiting to prevent the misuse. 
10. **3D Viewer Integration**
    **<u>Description</u>:** To preview models, a 3D viewer will be integrated into the platform for full interactivity.
    **<u>Proposed Solution</u>:** I will embed a web-based 3D viewer using Three.js that supports pan, zoom, rotate, and toggle controls. I will also add options for background color, grid visibility, etc. Generate a snapshot of the model, which will be used as a thumbnail preview.

11. **Decouple Modules into Public Libraries**
    **<u>Description</u>:** Regularly rewriting the project consumes unnecessary time and resources; a modular approach enhances reusability and long-term sustainability.
    **<u>Proposed Solution</u>:**  I will break OGV into reusable libraries/modules:
    - Upload handler
    - gcv conversion API wrapper
    - 3D viewer component
    - Authentication module 
    Each will be open-sourced and versioned so that future contributors can use or replace individual parts without breaking the whole system.

12. **CI/CD**
    **<u>Description</u>:** CI/CD is an important part of making a deployment update automatically and is essential nowadays as updating a deployment can include a few steps that might cover a portion of time and effort. This can be completely automated directly via GitHub as IaC.
    **<u>Proposed Solution</u>:** The project will be integrated with a CI/CD pipeline so that every commit automatically triggers a build and deployment process. This ensures that updates are seamlessly compiled and deployed, eliminating manual processes and significantly improving the deployment pipeline's efficiency.
    
13. **Security**
    **<u>Description</u>:** Implement robust security measures and compliance protocols to protect user data and system integrity. This includes secure authentication, controlled file storage, and measures to prevent abuse.
    **<u>Proposed Solution</u>:**
    -  User Authentication & Access Control:
       - Provide sign-in options via email, Google, or GitHub.
       - Ensure that only authenticated users can retain files beyond a
       session (unauthenticated files are removed immediately).
    - File Security & Compliance:
       - Use encryption and controlled access for secure file storage.
       - Adhere to STIG, OWASP, or Dependency-Check compliance for regular security audits.
    - Rate Limiting & Abuse Prevention:
       - Implement rate limiting on APIs and user actions.
       - Monitor and restrict abuse to prevent attacks and exploitation
       of the platform.

### Timeline
As mentioned in the Tasks details, I have added tasks that I think we should add to the project. All these tasks will be worked on once the coding period starts. During the coding period, I’ll document my experience through blogs, sharing insights, challenges, and solutions encountered throughout the project.. I’ll also keep updating the status in the channel about what has been done and what is being done.

- **Community Bonding Period (May 8 – June 1)**
    - During this period, my primary goal will be to familiarize myself further with BRL-CAD's practices and community.
    - I will actively engage with mentors through Zulip chat to learn more
    about the implementations we can apply to the project.
    - I will confirm the tech stack (Next.js, Nest.js, Three.js, SCSS,
    TypeScript, ESLint, Husky).
    - I will also work on the design to make it look complete so that we have a concrete image of what our project will look like at the end of the day.
    - I will also prepare for the setting up of the project as soon as possible by collecting additional information related to the features.
- **June 2 – July 14**
   - I will start this phase by committing the Boilerplate Setup. This part will be the outcome of the discussion from the previous period. It would take almost 2 days to complete the boilerplate.
   - I will develop the frontend, which was finalised in the previous period.
   - We can’t count Responsiveness and mobile-friendliness because this will be followed by the code. Responsiveness and mobile compatibility will be integrated into every module by design.
   - I will develop a dedicated conversion submodule leveraging BRL-CAD’s tools, which can also be published separately for future scalability. This module will handle the processing queue for incoming files, convert them to polygonal formats, and ensure smooth transformation with minimal user intervention.
   - Additionally, I will develop backend endpoints to generate downloadable converted files in various formats (.g, .stl, .obj, etc.).
   - These endpoints will allow users to select the desired file format or download all results as a zipped archive, making the converted models easily accessible from the user dashboard.
   - I will build a robust, drag-and-drop file uploader using a React component such as react-dropzone. This uploader will allow users to easily select or drag files (e.g., .g, .stl, .obj) for conversion. Once files are uploaded, they will be passed to the backend processing queue for conversion. easily select or drag files (e.g., .g, .stl, .obj) for conversion. Once files are uploaded, they will be passed to the backend processing queue for conversion.
   - I will implement a fully interactive 3D viewer using Three.js. This module will allow users to preview their converted 3D models directly within the browser. I will develop features that enable smooth pan, zoom, and rotation controls for an immersive viewing experience. Additionally, I will integrate options to toggle grid visibility, adjust background color, and switch view modes, ensuring that users can inspect models in detail.
- **July 14 - August 25**
  - During this period, I will submit my work, which I have done till now, for my mid-term evaluation, and I will start working on the next thing.
  - I will optimize the file upload and conversion system, ensuring it supports robust multi-file handling. This includes optimizing the upload experience, processing files in parallel or sequentially as needed, and providing clear feedback on the conversion progress.
  - I will optimize UI elements to deliver a smooth, modern, and responsive design that adapts seamlessly across different devices.
  - I will expand the user authentication and profile management system by integrating secure sign-in options (via OAuth and email & password) and enabling rich profile functionalities such as editing details and managing follow/unfollow actions.
  - I will implement advanced social interaction features, such as likes, comments, and sharing capabilities, and refine model management to support draft and publish states, ensuring users can easily manage and showcase their models.
  - I will decouple key functionalities into reusable public libraries to ensure long-term maintainability and ease of integration:
  - A dedicated module for file upload management.
  - A library that interfaces with BRL-CAD’s gcv tool for file conversion.
  - A modular Three.js–based viewer for interactive model previewing.
  - A reusable authentication component supporting multiple sign-in methods.
  - I will finalize and integrate a CI/CD pipeline that automates builds and deployments, ensuring that every commit is tested and deployed seamlessly.
  - I will implement robust security measures by enforcing secure authentication protocols and controlled file storage, while also applying rate limiting and compliance checks (using standards like STIG, OWASP, and Dependency-Check) to protect the system from vulnerabilities and abuse.
- **August 25 - September 1**
  This would be the final week for submitting the work, so I will focus on finalizing and documenting all completed tasks and adding further refinements as necessary. 

### Time Availability
I can easily dedicate around 24-28 hours per week. My college timings during weekdays are 9:00 AM to 3:30 PM IST. So, on weekdays, I will be able to work for 3-4:30 hours a day. I will dedicate the rest on the weekends. The examination, usually held in the first week of May, will not interfere with the coding timeline, which starts in June, and the exam would have already happened before that.
### Why BRL-CAD?
BRL-CAD is a great community, and working in a community where we get to know about 3D models via these cool projects provides an excellent opportunity to contribute to meaningful and innovative projects. I am passionate about open-source contributions, as they offer invaluable learning opportunities through collaboration with developers worldwide, and we get to work with programmers from around the world suggesting better ways to solve a problem, which can help me in being in a good developer. I deeply admire the BRL-CAD’s work, and this project would help me to learn a lot. Working on this Project would be an honor for me as it will likely be utilized by many contributors, marking a significant milestone in my development journey.
### Why Me?
- I have similar interests and skill sets required for this project and have actively invested time in these technologies.
- I have knowledge, strong interest and strong coding skills in C/C++, JavaScript, Node.js, React, Next.js, making submodules like npm-packages, Three.js, and Nest.js.
- I have experience in both frontend as well as backend development, gained through diverse project work.
- Additionally, I have more than 10 months of experience in my field job.
- I intend to remain actively involved with BRL-CAD beyond the conclusion of the GSoC program.
- I look forward to collaborating with talented developers worldwide, sharing ideas, and continuously learning to drive innovative solutions.
- I firmly believe in effective management and clear communication. I'll regularly share updates and proactively oversee the entire workflow to ensure smooth progress.