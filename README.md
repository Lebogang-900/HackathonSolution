# HackathonSolution
# AI-Powered Website Testing & Performance Analysis Workflow

# Overview

This project is an AI-powered website testing and performance analysis
workflow designed to automate the process of testing a web application

The Tester provides:

A URL to the website. 
We created this website for testing : https://customerhub-ten.vercel.app/login 

Instructions describing what should be tested.

The workflow then coordinates several specialised AI agents and testing
tools to explore the website, perform browser-based testing, execute
load tests, collect performance metrics, analyse the results, and
generate a final report.

The goal is to provide an end-to-end testing solution that reduces the
amount of manual effort required to perform functional, performance, and
load testing.

<img width="1355" height="735" alt="image" src="https://github.com/user-attachments/assets/52f2953e-9547-47c0-b7a1-b38fa768e1c5" />



# Main Components

1. When Chat Message Received: This is the entry point of the workflow.The user starts a testing request by providing the target URL and describing the testing requirements.

Instructions: Test the login process, check the main navigation, and perform a load test on the login endpoint. The message is passed to the main AI Agent for processing.

2. AI Agent

The AI Agent is the main orchestrator of the solution.

Its responsibilities include:
   Understanding the user's testing instructions.
   Determining which testing activities are required.
   Delegating work to specialised agents.
   Coordinating the different testing stages.
   Passing relevant information between agents.
   Ensuring that the requested URL and testing requirements are used throughout the workflow.

3. Browser Agent

The Browser Agent is responsible for website exploration and
browser-based testing.

It can be used to:
    Navigate through the website.
    Inspect pages.
    Follow links.
    Interact with UI elements.
    Test user journeys.
    Investigate functional behaviour.
    Identify potential browser or usability issues.

4. Load Test Agent

The Load Test Agent is responsible for performance and load-testing
activities. Its purpose is to determine how the target application behaves when
subjected to simulated traffic.

Depending on the user's instructions, it can help evaluate:
Response times.
    Application behaviour under load.
    Request success/failure rates.
    Performance degradation.
    Potential bottlenecks.

5. Metrics Collector

The Metrics Collector gathers additional technical performance
information.Its purpose is to provide measurable data that can be used by the
Analysis Agent when evaluating the application.

The collected information can include:
   Page performance metrics.
   Browser performance measurements.
   Lighthouse/PageSpeed results.
   Load-test results.


6. Analysis Agent

The Analysis Agent is responsible for combining and interpreting the
results produced by the different testing components.

It receives information from areas such as:
    Browser testing.
    Load testing.
    Performance metrics.
    Lighthouse/PageSpeed measurements.
    Other observations produced during the workflow.

The Analysis Agent can identify:
    Test failures.
    Functional issues.
    Performance concerns.
    Load-test results.
    Potential bottlenecks.
    Significant metrics.

7. Report Generator

The Report Generator is the final stage of the workflow. It converts the testing and analysis results into a structured report
that can be presented to the user.

The report can contain sections such as:
    Test overview.
    Target URL.
    User-provided requirements.
    Browser test results.
    Load-test results.
    Performance metrics.
    Identified issues.
    Important observations.

Recommendations for further investigation.


End-to-End Process

