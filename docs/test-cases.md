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

- **Signal Category**: Bug / Defect
- **Severity Level**: High
- **Confidence Level**: High
- **Recommended Action**: Escalate immediately

### Why This Case Matters

This is a baseline validation case.  
The input describes a clear operational failure affecting a core workflow. The assistant should classify confidently and escalate without hesitation, while avoiding technical diagnosis.

## Test Case 2: Feature Request Framed as Frustration

### Input
It’s really annoying that we can’t set permissions at the folder level. This should be standard.

### Expected Output (Summary)

- **Signal Category**: Feature Request / Product Feedback
- **Severity Level**: Low or Medium
- **Confidence Level**: High
- **Recommended Action**: Log and track

### Why This Case Matters

- This case tests the assistant’s ability to:
- ignore emotional tone
- avoid misclassifying frustration as a defect
- treat qualitative feedback as product input, not urgency

## Test Case 3: Implicit Churn Risk Without Explicit Threat


### Input  
We’re evaluating other tools because collaboration has been slowing us down lately.

### Expected Output (Summary)

- **Signal Category**: Churn / Revenue Risk
- **Severity Level**: Medium
- **Confidence Level**: Medium
- **Recommended Action**: Monitor for patterns

### Why This Case Matters

This input includes implied disengagement without an ultimatum.
The assistant should recognize potential risk while maintaining moderate confidence and avoiding over-escalation.

## Test Case 4: Explicit Churn Risk With Time Pressure

### Input
If this isn’t resolved this week, we’ll have to move to another platform.

### Expected Output (Summary)

- **Signal Category**: Churn / Revenue Risk
- **Severity Level**: High
- **Confidence Level**: High
- **Recommended Action**: Escalate immediately

### Why This Case Matters

This validates that the churn classification guardrail still allows escalation when **explicit indicators** are present.

## Test Case 5: Data / Integration Issue
### Input

Our CRM integration stopped syncing new records after the last API change.

### Expected Output (Summary)

- **Signal Category**: Data / Integration Issue
- **Severity Level**: Medium
- **Confidence Level**: High
- **Recommended Action**: Log and track

### Why This Case Matters

This case ensures that integration-related problems are not misclassified as core product bugs.

## Test Case 6: Vague Dissatisfaction, Insufficient Information

### Input

Things don’t feel reliable anymore.

### Expected Output (Summary)

- **Signal Category:** Feature Request / Product Feedback
- **Severity Level:** Low
- **Confidence Level:** Low
- **Recommended Action:** Request more information 

### Why This Case Matters

This is a critical safety test.
The assistant must:

- avoid inferring churn risk
- acknowledge ambiguity
- request clarification instead of guessing

This case directly validates restraint and uncertainty handling.
### Test Case 7: Emotional Language, Low Operational Impact

### Input
This new UI is terrible. I hate it.

**Expected Output (Summary)**

- **Signal Category**: Feature Request / Product Feedback
- **Severity Level**: Low
- **Confidence Level**: Medium
- **Recommended Action**: Monitor for patterns

### Why This Case Matters
The assistant must separate emotional expression from business impact and avoid unnecessary escalation.

## Test Case 8: Multiple Signals in One Message

### Input
Files aren’t syncing properly, and honestly this keeps happening. We’re losing patience.

### Expected Output (Summary)

- **Signal Category**: Bug / Defect
- **Severity Level**: High
- **Confidence Level**: Medium
- **Recommended Action**: Escalate immediately

### Why This Case Matters

This case tests prioritization when:

- an operational failure and
- dissatisfaction language

appear together.

## Test Case 9: Internal Operational Note (Neutral Tone)

### Input
Several tickets mention slower sync speeds on mobile, mostly from enterprise accounts.

### Expected Output (Summary)

- **Signal Category**: Bug / Defect
- **Severity Level**: Medium
- **Confidence Level**: High
- **Recommended Action**: Monitor for patterns or Log and track

### Why This Case Matters

This validates that the assistant works with internal summaries, not just customer complaints.