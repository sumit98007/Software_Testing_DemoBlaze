# JMeter Performance Testing Plan

## Overview

Create JMeter performance tests for https://demoblaze.com covering user workflows with varying load levels and generate a comprehensive analysis report.

## Implementation Steps

### 1. Initialize Git Repository & Project Structure

- Initialize Git repository
- Create project directory structure:
- `/part1-jmeter/` - JMeter test plans and reports
- `/part2-selenium/` - Maven project for Selenium tests
- `/part3-cucumber/` - Cucumber BDD tests
- Create `.gitignore` for Java/Maven/JMeter projects
- Create comprehensive README.md

### 2. JMeter Installation & Setup

- Download and install Apache JMeter (latest stable version)
- Verify Java is installed (required for JMeter)
- Create JMeter project files in `/part1-jmeter/`

### 3. Create JMeter Test Plan (.jmx file)

Create one test plan named `demoblaze_performance_test.jmx` with the following structure:

**Test Plan Configuration:**

- Name: "Demoblaze Performance Test"
- Add User Defined Variables if needed (base URL, etc.)

**Thread Group 1: 1 User**

- Number of Threads: 1
- Ramp-up Period: 10 seconds
- Duration: 20 seconds
- Scheduler enabled with duration 20s
- Action on Sampler Error: Continue

**Thread Group 2: 10 Users**

- Number of Threads: 10
- Ramp-up Period: 10 seconds
- Duration: 20 seconds
- Same configuration as above

**Thread Group 3: 20 Users**

- Number of Threads: 20
- Ramp-up Period: 10 seconds
- Duration: 20 seconds
- Same configuration as above

**Thread Group 4: 50 Users**

- Number of Threads: 50
- Ramp-up Period: 10 seconds
- Duration: 20 seconds
- Same configuration as above

### 4. HTTP Samplers for Each Thread Group

For EACH thread group, add the following HTTP Request samplers:

1. **Homepage** (with 300ms delay)

- Method: GET
- Path: /
- Add Constant Timer: 300ms

2. **Sign Up Page**

- Method: POST
- Path: /signup
- Body Data: JSON with username and password

3. **Login**

- Method: POST
- Path: /login
- Body Data: JSON with username and password

4. **Browse Categories - Phones**

- Method: GET
- Path: /bycat endpoint or appropriate API

5. **Browse Categories - Laptops**

- Method: GET
- Similar to phones

6. **Browse Categories - Monitors**

- Method: GET
- Similar to phones

7. **Add to Cart**

- Method: POST
- Path: /addtocart
- Body Data: Product ID

8. **View Cart**

- Method: GET
- Path: /viewcart

### 5. Add Response Assertions

For each HTTP Request sampler, add:

- Response Assertion
- Pattern Matching: Contains
- Expected patterns: Success indicators (200 status, specific text, etc.)

### 6. Add Listeners to Each Thread Group

Add these 4 listeners to EACH thread group:

1. View Results Table
2. View Results Tree
3. Graph Results
4. Aggregate Report

### 7. Execute Tests

- Run the complete test plan
- Collect results from all listeners
- Take screenshots of:
- Tree Results showing request/response headers
- Graph Results showing performance graphs
- Aggregate Report showing statistics

### 8. Create Performance Summary Report

Create a document (Word/PDF) with maximum 2 pages containing:

**Section 1: Test Configuration Overview**

- Test environment details
- Thread group configurations
- Test scenarios covered

**Section 2: Results Analysis**

- **Table Results**: Request and response headers screenshots
- **Tree Results**: HTTP request/response data screenshots
- **Aggregate Report Metrics**:
- Throughput per second (Throughput/Sec)
- Throughput per minute (Throughput/Min)
- Minimum response time for each sampler
- Maximum response time for each sampler
- Average response time
- Error percentage

**Section 3: Performance Analysis**

- Analysis of system behavior under different loads (1, 10, 20, 50 users)
- Bottlenecks identified
- Response time trends
- Throughput analysis
- Recommendations

**Section 4: Screenshots**

- Graph Results (showing all thread groups)
- Tree Results with request/response details

### 9. Final Deliverables

- `demoblaze_performance_test.jmx` - JMeter test plan file
- `Performance_Test_Report.pdf` - Analysis report with screenshots
- Screenshots folder with all captured images

## Key Notes

- Demoblaze.com uses API endpoints for sign up/login (POST requests with JSON)
- May need to inspect network traffic in browser DevTools to identify exact API endpoints
- Use HTTP Header Manager to set Content-Type: application/json for POST requests
- Consider using CSV Data Set Config for multiple user credentials if needed

## To-dos

- [ ] Download and install Apache JMeter, verify Java installation
- [ ] Create JMeter test plan with 4 thread groups (1, 10, 20, 50 users)
- [ ] Add HTTP request samplers for all test scenarios (signup, login, browse, cart)
- [ ] Add response assertions to each HTTP sampler
- [ ] Add 4 listeners (Table, Tree, Graph, Aggregate) to each thread group
- [ ] Run JMeter tests and collect results/screenshots
- [ ] Write performance analysis report with metrics and screenshots
