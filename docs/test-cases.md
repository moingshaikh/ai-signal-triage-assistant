### Test Cases – AI Signal Triage Assistant

This document contains representative test cases used to validate the behavior of the **AI Signal Triage Assistant**.

The goal of these tests is **not** to prove model intelligence, but to verify:

- consistency of classification
- appropriate severity assessment
- explicit confidence handling
- responsible behavior under ambiguity

Each test case includes:

- raw input signal
- expected classification behavior
- rationale for why the case matters

## Test Case 1: Clear Bug, High Business Impact

### Input

Since yesterday’s update, files are no longer syncing on mobile. Our team can’t access shared folders, and this is blocking daily work.

### Expected Output (Summary)

- Signal Category: **Bug / Defect**
- Severity Level: **High**
- Confidence Level: **High**
- Recommended Action: **Escalate immediately**

### Why This Case Matters

This is a baseline validation case.  
The input describes a clear operational failure affecting a core workflow. The assistant should classify confidently and escalate without hesitation, while avoiding technical diagnosis.

## Test Case 2: Feature Request Framed as Frustration

### Input
It’s really annoying that we can’t set permissions at the folder level. This should be standard.

### Expected Output (Summary)

- Signal Category: **Feature Request / Product Feedback**
- Severity Level: **Low or Medium**
- Confidence Level: **High**
- Recommended Action: **Log and track**

### Why This Case Matters

- This case tests the assistant’s ability to:
- ignore emotional tone
- avoid misclassifying frustration as a defect
- treat qualitative feedback as product input, not urgency

## Test Case 3: Implicit Churn Risk Without Explicit Threat


### Input  
We’re evaluating other tools because collaboration has been slowing us down lately.

### Expected Output (Summary)

- Signal Category: Churn / Revenue Risk
- Severity Level: Medium
- Confidence Level: Medium
- Recommended Action: Monitor for patterns

### Why This Case Matters

This input includes implied disengagement without an ultimatum.
The assistant should recognize potential risk while maintaining moderate confidence and avoiding over-escalation.