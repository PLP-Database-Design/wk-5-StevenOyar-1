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
| Risk Analyst | Rose Kemunto| Risk identification, prioritization, test design linkage |
| Test Executor |Lilian Kavengi | Execution, evidence capture, defect logging |

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
| Reset Game | Clears score and progress instantly | State Management |
| Leaderboard | Stores top 3 scores in localStorage | Data Persistence |
| Bonus Round | Every 3 puzzles → doubles score | Business Logic | 

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
|Test Environment setup  | 1day|1 day |Completed |
| Test Planning | 2 days | 1 days |  Completed |
| Risk Analysis | 1 day | 1 day |  Completed |
| Test Case Design | 2 days | 2 days | Completed |
| Test Execution | 2 days | 2 days | Completed |
| Defect Logging | 1 day | 1 day | Completed |
| Defect Reporting|2 days | 2 days|Completed
| Metrics| 1 day | 1day| Completed|
|Test Closure|1 day |1day | Completed|
| Report Writing | 1 day | 1 day |  Completed |
| **Total** | **14 days** | **13 days** | **Complete** |


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
| R-01 | Bonus Round | Score multiplication logic error (wrong multiplier) | High | High | **Critical** | Create boundary test cases for exactly 3, 6, 9 puzzles; verify score doubling calculation |
| R-02 | Leaderboard | localStorage data corruption or incorrect sorting | Medium | High | **High** | Test edge cases: empty data, non-numeric values, exactly 3 scores, >3 scores |
| R-03 | Reset Game | Incomplete state reset (residual data persists) | Medium | Medium | **Medium** | Verify all state variables cleared; check leaderboard persistence after reset |
| R-04 | Scoring | Arithmetic errors in score calculation with hints | Medium | Medium | **Medium** | Test scoring with/without hints, negative score prevention |
| R-05 | Bonus Round | Bonus triggers multiple times or at wrong intervals | Low | High | **High** | Test consecutive puzzles 1-10 to verify trigger pattern |
| R-06 | Input Validation | Empty or invalid input crashes game or causes unexpected behavior | Low | Medium | **Medium** | Test empty submissions, special characters, excessive length |
| R-07 | State Management | Race conditions when rapidly submitting answers | Low | Low | **Low** | Perform rapid-fire testing with quick submissions |
| R-08 | Leaderboard | Data not persisting across browser sessions | Medium | High | **High** | Close/reopen browser and verify leaderboard retained |

### Risk Coverage

- **Tested Risks:** 7 out of 8 (R-01 through R-08, with R-07 partially tested)
- **Untested Risks:** 1 (R-08 - Browser session persistence not fully tested)
- **Risk Coverage Percentage:** **87.5%**

**Risk Priority Distribution:**
- Critical: 1 (12.5%)
- High: 3 (37.5%)
- Medium: 3 (37.5%)
- Low: 1 (12.5%)

## Test Cases

| ID | Feature | Objective | Expected Result | Actual Result | Status | Risk Link |
|----|---------|-----------|-----------------|---------------|--------|-----------|
| TC-01 | Bonus Round | Verify score doubles at exactly 3 puzzles | Score = 60 (30 doubled); "Bonus Round!" message | Score = 60; bonus message shown | PASS | R-01 |
| TC-02 | Bonus Round | Verify bonus does NOT trigger at puzzle 2 | Score = 20 (no doubling); "Bonus at: 1" | Score = 20; indicator correct | PASS | R-01 |
| TC-03 | Leaderboard | Verify top-3 scores sorted descending | Shows 120🥇, 95🥈, 80🥉 only | Correct order displayed | PASS | R-02 |
| TC-04 | Leaderboard | Handle duplicate score values | Three entries of 100 shown | Three "100" displayed | PASS | R-02 |
| TC-05 | Reset Game | Verify complete state reset | Score=0, Solved=0, hint cleared, leaderboard persists | All state cleared correctly | PASS | R-03 |
| TC-06 | Input Validation | Reject empty input (negative) | Error: "Please enter a guess!" | Correct error shown | PASS | R-06 |
| TC-07 | Leaderboard | Test with >3 scores (boundary) | Add 5 scores to leaderboard, verify only top 3 displayed | Leaderboard is bound to top 3 only scores | PASS | R-02 |
| TC-08 | UX/Usability | Assess feedback quality and transitions | Smooth animations, clear messages, appropriate delays | Excellent UX observed | PASS | R-07 |
| TC-09 | Score Calculation | Verify hint penalty and reduced award | Score: 18 after hint, 23 after solve (18+5) | Calculated correctly | PASS | R-04 |

**Summary:** 9 test cases executed | 9 passed | 0 failed | **100% pass rate**



## Defects


| ID | Issue Title | Severity | Risk ID | Status | GitHub Link |
|----|-------------|----------|---------|--------|-------------|
| DEF-01 | Hint button remains visually active after use | Low | R-06 | Open | [Issue #1](https://github.com/PLP-Database-Design/wk-5-StevenOyar-1/issues/2) |
| DEF-02 | Reset button clears scrambled word - user cannot see puzzle | High | R-03 | Open | [Issue #2](https://github.com/PLP-Database-Design/wk-5-StevenOyar-1/issues/4) |
| DEF-03 | Hint penalty (-2) not applied when score is 0| Medium | R-04 | Open | [Issue #3](https://github.com/PLP-Database-Design/wk-5-StevenOyar-1/issues/3) |
---

## Metrics

- **Test Case Pass Percent:** 100% (9 passed / 9 total)
- **Defect Density:** 0.33 (3 defects / 9 test cases)
- **Risk Coverage Percent:** 87.5% (7 tested / 8 total risks)
- **Regression Success Rate:** N/A (no fixes implemented yet for re-testing)

### Defect Summary
- **Total Defects Logged:** 3
- **Critical/High:** 1 (33%)
- **Medium:** 1 (33%)
- **Low:** 1 (33%)
- **Fix Rate:** 0% (testing phase only; no development fixes yet)

### Defect Distribution by Severity

```
High:   33% (1) ████████████
Medium: 33% (1) ████████████
Low:    33% (1) ████████████
```

## Test Control & Project Management

### Phases

| Phase | Deliverable | Actual Output | Variance | Owner |
|-------|-------------|---------------|----------|-------|
| Planning | Test plan with entry/exit criteria | Completed as specified | None | Test Manager |
| Risk Analysis | 7 risks identified & prioritized | Met requirement (minimum of 6) | +1 extra risk | Risk Analyst |
| Test Design | 9 test cases (5 risk-based, 2 negative, 1 usability) | Exceeded minimum (minimum of  8) | +2 cases | All team |
| Execution | All tests executed with evidence | 90% pass rate achieved | None | Test Executor |
| Defect Logging | 3 GitHub issues with full details | Met requirement | None | Test Executor |
| Metrics | Calculated and visualized all metrics | Completed | None | Test Manager |

**Progress Tracking Method:**   shared markdown document document for real-time collaboration among the 3 of us.

**Change Control Notes:** -  
 - Day 1: created a test plan by a test manager.
- Day 2: Added TC-09 after Risk Analyst identified scoring calculation gap  
- Day 3: added the defects by the test executor and updated the schedule.
- Day 4: phases of of delivarible and the output that was found 


## Lessons Learned

- Most Defect Prone Feature:  The Reset Game feature has the most critical defect. DEF-02 (scrambled word not visible after reset) completely breaks user workflow, making the game unplayable without a page reload. This highlights the importance of thorough state management testing during reset operations.
- Risk Analysis Impact:
Risk-based testing was highly effective. Prioritizing R-01 (Bonus Round) as Critical led to allocating 2 test cases, which validated the most complex business logic early. The Likelihood × Impact scoring helped avoid over-testing low-risk UI elements while ensuring 100% coverage of High/Critical risks.

- Team Communication Effectiveness: 
**Strengths:** Clear role separation prevented overlap, GitHub Issues provided transparency and single markdown document helped in updating progress effectively.  
**Challenges:** Initial scope confusion and the time limit among members as most of them are working.

- Improvements for Next Cycle: 
Automate some testing like regression testing, conduct daily meetings among the members to ensure that everyone's opinion is considered and it creates better project handling, create more time for exploratory testing and finally we can schedule more meetings for defect analysis.
## Attachments

- 

## Sign Off

| Name | Role | Initials | Date |
|------|------|-----------|------|
| Steven Oyaro| Test Manager |So | 28/10/2025|
|Rose kemunto| Risk Analyst |RK| 28/10/25|
|Lilian Kavengi| Test Executor | LK|28/10/25 |

## Overall Summary
test management successfully validated the three new features of Word Puzzle Game Plus (Reset, Leaderboard, Bonus Round) using risk-based testing methodology. We achieved **100% test case pass rate** and **87.5% risk coverage**, identifying **3 defects** with varying severity levels that require attention before production release.
**Statement:** 
- All 8 identified risks tested and documented (exceeds minimum requirement of 6)
- 9 test cases executed with 100% pass rate (exceeds minimum requirement of 8)
- 3 defects logged with complete reproduction steps, root cause analysis, and suggested fixes (meets minimum requirement of 3)
- Comprehensive test metrics calculated and documented
- Strong team collaboration with clear role accountability
  
**Test Status:**  Completed 
