# HackathonSolution
AI-Powered Website Testing & Performance Analysis Workflow

Overview

This project is an AI-powered website testing and performance analysis
workflow designed to automate the process of testing a web application

The Tester provides:

A URL to the website.

Instructions describing what should be tested.

The workflow then coordinates several specialised AI agents and testing
tools to explore the website, perform browser-based testing, execute
load tests, collect performance metrics, analyse the results, and
generate a final report.

The goal is to provide an end-to-end testing solution that reduces the
amount of manual effort required to perform functional, performance, and
load testing.

<img width="1436" height="798" alt="image" src="https://github.com/user-attachments/assets/3954c20c-15d2-4797-b603-641c7884397e" />


Main Components

1. When Chat Message Received

This is the entry point of the workflow.

The user starts a testing request by providing the target URL and
describing the testing requirements.

Instructions:
Test the login process, check the main navigation,
and perform a load test on the login endpoint.

The message is passed to the main AI Agent for processing.

2. AI Agent

The AI Agent is the main orchestrator of the solution.

Its responsibilities include:

Understanding the user's testing instructions.

Determining which testing activities are required.

Delegating work to specialised agents.

Coordinating the different testing stages.

Passing relevant information between agents.

Ensuring that the requested URL and testing requirements are used
throughout the workflow.

The AI Agent acts as the central controller rather than performing every
test itself.

OpenRouter Chat Model

The OpenRouter Chat Model provides the language-model capabilities used
by the main AI Agent.

It allows the agent to:

Interpret natural-language instructions.

Reason about testing requirements.

Decide which tools and agents should be used.

Coordinate the overall workflow.

Simple Memory

Simple Memory maintains relevant conversational context.

This allows the workflow to retain information such as:

The target URL.

Testing instructions.

Previous information provided during the conversation.

Context required by the agents during the testing process.

Specialised Testing Agents

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

The Browser Agent receives instructions from the main AI Agent and uses
browser-related tools to perform the requested exploration.

OpenRouter Chat Model1

This model provides the reasoning capabilities for the Browser Agent.

It helps the agent determine:

Which pages to visit.

Which actions to perform.

What elements to interact with.

Whether the observed behaviour matches the requested test.

fetch_page

fetch_page retrieves webpage information for inspection.

It can be used when the agent needs to:

Read webpage content.

Inspect page information.

Understand the structure of a page.

Gather information before performing further testing.

playwright_explore

playwright_explore provides browser automation capabilities.

It can be used to perform actions such as:

Opening pages.

Clicking elements.

Entering information.

Navigating through the application.

Testing interactive workflows.

4. Load Test Agent

The Load Test Agent is responsible for performance and load-testing
activities.

Its purpose is to determine how the target application behaves when
subjected to simulated traffic.

Depending on the user's instructions, it can help evaluate:

Response times.

Application behaviour under load.

Request success/failure rates.

Throughput.

Performance degradation.

Potential bottlenecks.

OpenRouter Chat Model2

This model provides the reasoning capabilities for the Load Test Agent.

It helps determine how the requested load test should be structured
based on the user's instructions and the target application.

k6 Load Test

The k6_load_test tool performs the actual load-testing activity using
k6.

It can be used to simulate requests against the target application and
collect performance results.

Typical load-test information may include:

Virtual users.

Request duration.

Throughput.

Error rates.

HTTP response codes.

Threshold results.

5. Metrics Collector

The Metrics Collector gathers additional technical performance
information.

Its purpose is to provide measurable data that can be used by the
Analysis Agent when evaluating the application.

The collected information can include:

Page performance metrics.

Browser performance measurements.

Lighthouse/PageSpeed results.

Load-test results.

Other available performance indicators.

OpenRouter Chat Model3

This model supports the Metrics Collector by helping interpret the
metrics that are collected and determining which information is relevant
to the overall testing request.

lighthouse_pagespeed

The lighthouse_pagespeed tool retrieves Lighthouse/PageSpeed-related
information.

This can provide insight into areas such as:

Page performance.

Loading behaviour.

Web performance metrics.

General website quality indicators.

browser_metrics

The browser_metrics tool collects additional metrics from
browser-based testing.

These metrics can supplement the results obtained from the browser
exploration and Lighthouse/PageSpeed analysis.

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

Areas that may require further investigation.

OpenRouter Chat Model4

This model provides the reasoning capabilities used by the Analysis
Agent to interpret the testing results and produce meaningful findings.

7. Report Generator

The Report Generator is the final stage of the workflow.

It converts the testing and analysis results into a structured report
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

