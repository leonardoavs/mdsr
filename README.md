
# System Explanation

**Backend:** We implemented a system based on microservices and communication gateways using Java and the MuleSoft Anypoint Platform. The gateways were consumed by the frontend widgets to retrieve information from our core systems. These gateways handled validations, data transformations, endpoint consolidation, and standardized response structures that could be consumed by the frontend. I implemented these components using AI coding tools, including the corresponding test cases.

**Frontend:** The frontend was implemented in React as a widget framework that consumed backend gateway services for different clients. For example, we had social media widgets, credit score widgets, report widgets, and others. These were implemented using React hooks to communicate with the backend, sometimes requiring bidirectional communication.

### Original Requirement

One specific requirement was to implement a social media widget that allowed customers to connect their social media accounts to our system through backend gateway services.

The widget needed to provide a responsive interface for different clients and allow users to authorize connections to their social media networks.

On the backend, the system retrieved and analyzed social media information to identify potential information leaks and alert users about information that could potentially affect their credit scores.

This implementation involved REST APIs, MuleSoft, Java, and the Anypoint Platform for backend integration, along with React and TypeScript for the frontend widgets.

# How I Use AI Coding Tools

For a specific feature, I use GitHub Copilot with different models. Sometimes I use ChatGPT for planning and Claude for code implementation. The context provided to these models comes from the existing repository, which could be either the backend or frontend of the application.

I also use AI to generate a small SDD (Spec-Driven Development) specification based on the details and requirements that we get from Jira. Even images from Figma are provided to the agent to analyze the look and feel required for the CSS implementation.

### Having the SDD, I break the implementation into several tasks:

1. Analyze the requirement SDD-001, where 001 represents the requirement number.
2. Analyze the existing implementation and dependencies in the repository.
3. Based on the analysis, create an implementation plan and split the changes into subtasks:

   - Implement the code.
   - Generate or update the test cases based on the requirements.
   - Review against existing components or API contracts.
   - If there are any issues, fix them until no errors remain.
   - **Manual Tasks:**
     1. These are tasks that I usually perform manually. I run the application locally and test what was generated.
     2. Review the generated code to verify that it is aligned with the existing codebase and architecture.

This process was used for both backend and frontend development. We also had agent instruction files and smaller specialized agents that helped us with the specific coding requirements for each layer.

# What the Agent Implemented Versus My Contributions

**The agent** helped me implement code, CSS, unit tests, analyze issues and bugs, and fix coding problems that we encountered and allowed it to correct.

For the backend, the AI tools helped implement microservices and gateways, including REST API integrations, validations, data transformations, and standardized responses for frontend consumption.

One example was the social media integration, where the backend gateways connected our system with different social media networks. The purpose was to retrieve information, analyze potential information exposure, and alert users when relevant information could potentially affect their credit scores.

This integration was implemented using REST APIs, MuleSoft, Java, and the MuleSoft Anypoint Platform.

For the frontend, AI tools were used to implement React widgets that allowed clients to interact with these backend services, including credit score and social media widgets.

**My contributions** were mainly focused on reviewing the implementation and making architectural decisions, such as API design, integration strategy, validation of the implemented code, and validation of business requirements.

Moreover, I reviewed the generated code, moved the PRs through the approval process, and kept stakeholders aligned with the current designs and ongoing implementation of both backend and frontend systems.

Although AI tools helped generate a substantial part of the implementation, I remained responsible for the architectural decisions, code review, business requirements, and final validation.

# Testing

The unit test generation was done by the AI agent. I reviewed and verified that all the test cases were implemented, analyzed whether there were duplicated or missing scenarios, and instructed the AI to fix any issues.

Sometimes manual testing was necessary for cases that the AI could not reproduce.

The tools that we used included Vitest, Chromatic/Storybook, MUnit, JUnit, and others.

The AI agents had instructions and commands to execute the tests and implement the test cases according to the project requirements. In case of failures, they also had instructions to analyze and fix the issues.

However, I personally reviewed the test results, validated the implementation, and performed manual testing when necessary to ensure that the solution met the requirements.

# An Agent Error That Was Fixed

In the frontend, we provided the agent with instructions to create the look and feel of the web pages, but there were some corner cases that it was not able to resolve correctly.

For example, when switching from desktop to mobile view, the agent did not correctly handle the HTML tables, causing issues with the responsive layout.

To fix this issue, we implemented Table Stacking for Responsive UIs, allowing the tables to adapt to smaller screens by stacking the table content vertically instead of keeping the traditional desktop table layout.

After implementing and validating the fix, we provided the agent with additional instructions to use this Table Stacking approach for future development whenever similar responsive table scenarios appeared.

By doing this, we corrected the original issue and prevented similar failures by teaching the agent how to handle these specific cases.

This was also an example of why manual validation and code review were important, even when the implementation and tests were generated using AI.

# Conclusions

The main benefit of using all these tools was AI-assisted development. Development time was significantly reduced, especially for repetitive coding tasks.

The final implementation passed our automated tests and manual validations, went through the PR approval process, and was successfully integrated into the application.

Meanwhile, we were able to focus more on architectural decisions, code quality, testing, and system integration across both backend and frontend systems.

AI helped accelerate the implementation, but the responsibility for ensuring that the solution was reliable and met the business requirements remained with us.

# Additional Work

Currently, we are working on implementing an agent that takes Jira issues, enriches the Jira documentation, analyzes the requirements, and asks questions about anything that could block development.

Once these questions have been answered, the same agent will be able to implement the code, generate and execute tests, commit the changes, and submit a PR for human review.

The goal is to automate much of the development process, even outside working hours, while keeping human supervision focused on architectural decisions, implementation analysis, validation, and code review.

This is still ongoing work and is currently in its early stages.
