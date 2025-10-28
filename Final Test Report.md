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
| Test Executor |Kavengi Lilian Kathini | Execution, evidence capture, defect logging |

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

 | Feature | Risk Description | Likelihood | Impact | Priority | Mitigation Strategy |
|----|---------|------------------|------------|--------|----------|---------------------|
| R-01 | Bonus Round | Score multiplication logic error (wrong multiplier or timing) | High | High | *Critical* | Create boundary test cases for exactly 3, 6, 9 puzzles; verify score doubling calculation |
| R-02 | Leaderboard | localStorage data corruption or incorrect sorting | Medium | High | *High* | Test edge cases: empty data, non-numeric values, exactly 3 scores, >3 scores |
| R-03 | Reset Game | Incomplete state reset (residual data persists) | Medium | Medium | *Medium* | Verify all state variables cleared; check leaderboard persistence after reset |
| R-04 | Scoring | Arithmetic errors in score calculation with hints | Medium | Medium | *Medium* | Test scoring with/without hints, negative score prevention |
| R-05 | Bonus Round | Bonus triggers multiple times or at wrong intervals | Low | High | *High* | Test consecutive puzzles 1-10 to verify trigger pattern |
| R-06 | Input Validation | Empty or invalid input crashes game or causes unexpected behavior | Low | Medium | *Medium* | Test empty submissions, special characters, excessive length |
| R-07 | State Management | Race conditions when rapidly submitting answers | Low | Low | *Low* | Perform rapid-fire testing with quick submissions |
| R-08 | Leaderboard | Data not persisting across browser sessions | Medium | High | *High* | Close/reopen browser and verify leaderboard retained |


### Risk Coverage

* *Tested Risks:* 7 out of 8 (R-01 through R-08, with R-07 partially tested)
* *Untested Risks:* None (all identified risks have associated test cases)
* *Risk Coverage Percentage:* *87.5%*

*Risk Priority Distribution:*
* Critical: 1 (12.5%)
* High: 3 (37.5%)
* Medium: 3 (37.5%)
* Low: 1 (12.5%)



## Test Cases
| ID | Feature | Objective | Expected Result | Actual Result | Status | Risk Link |
|----|---------|-----------|----------------|---------------|--------|-----------|
| TC-01 | Bonus Round | Verify bonus triggers at 3rd puzzle | After solving 3rd puzzle, message "Bonus Round! Score doubled!" appears and score doubles | ❌ Score doubles *before* 3rd puzzle award, causing incorrect calculation | *FAIL* | R-01 |
| TC-02 | Leaderboard | Verify top-3 sorting with scores 5, 12, 8 | Leaderboard displays: 1st: 12 🥇, 2nd: 8 🥈, 3rd: 5 🥉 | ❌ Leaderboard updates after *every correct answer, not just reset. Shows cumulative scores incorrectly | **FAIL* | R-02 |
| TC-03 | Reset Game | Verify complete state reset | Score=0, Solved=0, Bonus indicator resets, input cleared, message shown | ✅ All state cleared correctly | *PASS* | R-03 |
| TC-04 | Bonus Round | Verify 6th and 9th puzzle also trigger bonus | Bonus message appears at puzzles 3, 6, 9 with score doubling | ✅ Bonus triggers correctly at multiples of 3 | *PASS* | R-01, R-05 |
| TC-05 | Scoring | Verify hint penalty and reduced award | Using hint: -2 points immediately, +5 on correct (vs +10 without hint) | ✅ Hint deducts 2 points, correct answer with hint adds 5 | *PASS* | R-04 |
| TC-06 | Input Validation | Submit empty guess | Error message "Please enter a guess!" displayed | ✅ Error shown, no crash | *PASS* | R-06 |
| TC-07 | Leaderboard | Verify persistence across sessions | Close browser, reopen game → leaderboard data retained | ✅ Data persists correctly via localStorage | *PASS* | R-08 |
| TC-08 | Scoring | Verify negative score prevention with hints | Use 3 hints at start (score should not go below 0) | ✅ Score cannot go negative (Math.max protection) | *PASS* | R-04 |
| TC-09 | Leaderboard | Test with >3 scores | Add 5 scores to leaderboard, verify only top 3 displayed | ❌ Each puzzle adds to leaderboard. Array grows unbounded beyond 3 | *FAIL* | R-02 |
| TC-10 | Usability | New Puzzle button functionality | Click "New Puzzle" → new scrambled word loads, state resets for current puzzle | ✅ Works as expected | *PASS* | R-07 |
| TC-11 | Reset Game | Verify leaderboard persists after reset | Reset game → leaderboard data should remain intact | ✅ Leaderboard not cleared by reset (as intended) | *PASS* | R-03 |
| TC-12 | Input Validation | Case sensitivity test | Enter answer in UPPERCASE, lowercase, MiXeD case | ✅ All cases accepted (normalized to lowercase) | *PASS* | R-06 |

### Test Summary
* *Total Test Cases:* 12
* *Passed:* 9 (75%)
* *Failed:* 3 (25%)
* *Pass Rate:* *75%* (below 85% target due to critical defects)

---


## Defects

| ID | Issue Title | Severity | Risk ID | Status | GitHub Link |
|----|-------------|----------|---------|--------|-------------|
| | | | | | |


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
| | Test Executor |LKK |28/10/2025|

## Overall Summary

**Statement:** 

**Test Status:** ☐ Completed / ☐ In Progress / ☐ Deferred
ID
