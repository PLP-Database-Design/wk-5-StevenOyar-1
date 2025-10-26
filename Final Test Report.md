# 🧪 Final Group Test Report Template — Word Puzzle Game Plus

**Level:** Intermediate QA | **Week 5:** Test Management

**Course:** Software Testing & Quality Assurance  
**Module:** Test Management (Week 5)  
**Project Type:** Group Assessment  
**Submission Date:** 2025-10-28

## Team Information

| Role | Name | Responsibilities |
|------|------|------------------|
| Test Manager | | Planning, scheduling, coordination, metric tracking |
| Risk Analyst | | Risk identification, prioritization, test design linkage |
| Test Executor | | Execution, evidence capture, defect logging |

## Group Rules

- Each student must belong to only one group.
- Duplicate membership or multiple submissions will result in invalidation.
- Every group member must contribute towards this project

## Project Overview

**System Under Test:** Word Puzzle Game Plus  
**Technology Stack:** HTML, CSS, JavaScript  
**Environment:** Chrome Browser (Desktop)

### Features Under Test

| Feature | Description | Risk Category |
|---------|-------------|---------------|
| Reset Game | Clears score and progress instantly | |
| Leaderboard | Stores top 3 scores in localStorage | |
| Bonus Round | Every 3 puzzles → doubles score | |

## Test Plan

### Objectives

- ensure that the Word Puzzle Game works has expected from word unscrample, guess validation  works has expected.
- all scoring rules provided are applied to the game correctly
- The leadersboard should pesist has expected from the rules. i.e the top 3 scores should be displayed only.
- Bonus is applied correctly to the game after every 3 puzzles. 
-  Reset button clears scores and progrogress but the leadersboard is not interfered with.
- testing the input fields and all buttons are working seemlessly has expected.

### Scope

**In Scope:**
- chrome browser destop only test
- the score, solved and bonus counters working has expected.
- leadersboard saved to localStorage even after reply or reset 
- rules display
- input field are accepting the input from the user.
- input validation
- hint button apply the deduction of 2 points and the award is changed to 5 
- bonus is triggered at the third correct guess and the points are doubled.
- correct submit guess is adding 10 points to the score.
- new puszzle changes the puzzle to be solved.
- reset button clear the puzzle score, solved data 
- leadersboard should have the top 3 scores saved in the browser.
- Rules should be displayed for testing the accurancy of the game.

**Out of Scope:**
-  backend integration
- small screen responsiveness
- other browsers testing environment other than chrome desktop.
- user authetication
- the scores analytics.
-  other scores that are not in top 3
- the length of the guessed work
- UI and css styling



### Tools & Resources
| category | Tool/resorces| purpose|  
|----|---------|------------------|
|Browser|Chrome Browser (Desktop) |Test envriorment|
|defect tracking and issuues|Github issues|bug  and defect documentation|
|evidence collection |Screenshot| evidence for bugs and defects|
|documentation |Markdown|Test plan and metric analysis are written in markdown |
|collaboration tool|Github issues or github repo issues| collaboration among all team members and progress tracking|

### Schedule

| Phase | Planned Duration | Actual Duration | Status |
|-------|------------------|-----------------|--------|
| Test planning| 1 day  | 1 day| | completed
|risk analysis | 2 days | |Not started |
| Test case design| 2 days| |Not Started |
|Test Environment setup  | 1day| |Not started |
|Test execution | 2 days| |Not Started |
| Defect Reporting|2 days | | Not Started|
| Metrics| 1 day | | Not Started|
|Test Closure|1 day | |Not Started |


## Entry Criteria
- chrome browser desktop version installed and functional 
- Test plan created by Test manager and approved 
- risk analysis completed
- test case designed , documented and reviewed
- github repository 
- localStorage enabled in chrome browser.

## Exit Criteria
- All planned test cases are executed
- Risk coverage is more than 85%
- Test case pass rate is more than 95% 
- all defects critical, high and low documented(Minimum 3 defects logged in GitHub Issues with complete documentation)
- Test metrics calculated and documented.
- Test report completed
- Test manager sign-off obtained.
## Risk Analysis

### Risks

| ID | Feature | Risk Description | Likelihood | Impact | Priority | Mitigation Strategy |
|----|---------|------------------|------------|--------|----------|---------------------|
| | | | | | | |

### Risk Coverage

- Tested Risks Percent: 
- Untested Risks Percent: 

## Test Cases

| ID | Feature | Objective | Expected Result | Actual Result | Status | Risk Link |
|----|---------|-----------|----------------|---------------|--------|-----------|
| | | | | | | |

## Defects

| ID | Issue Title | Severity | Risk ID | Status | GitHub Link |
|----|-------------|----------|---------|--------|-------------|
| | | | | | |

## Metrics

- Test Case Pass Percent: 
- Defect Density: 
- Risk Coverage Percent: 
- Regression Success Rate: 

### Defect Summary

- Total Defects Logged: 
- Critical High: 
- Fix Rate: 

## Test Control & Project Management

### Phases

| Phase | Deliverable | Actual Output | Variance | Owner |
|-------|-------------|---------------|----------|-------|
| | | | | |

**Progress Tracking Method:**  
**Change Control Notes:**

## Lessons Learned

- Most Defect Prone Feature: 
- Risk Analysis Impact: 
- Team Communication Effectiveness: 
- Improvements for Next Cycle: 

## Attachments

- 

## Sign Off

| Name | Role | Initials | Date |
|------|------|-----------|------|
| | Test Manager | | |
| | Risk Analyst | | |
| | Test Executor | | |

## Overall Summary

**Statement:** 

**Test Status:** ☐ Completed / ☐ In Progress / ☐ Deferred
