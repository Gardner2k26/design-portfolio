
# SupplySight
## UX Evaluation and Design Iteration

**Designer:** Naja Gardner
**Project Type:** Independent Digital Product Design Concept
**Evaluation Method:** Self-Conducted Functional and Heuristic Review
**Baseline:** SupplySight Version 1
**Updated Product:** SupplySight Version 2

---

## 1. Project Overview

SupplySight is an independent digital product design concept
exploring how supply chain personnel can monitor inventory
discrepancies, investigate issues, and document corrective
actions through a centralized interface.

The product was designed and developed using HTML5, CSS3,
and JavaScript.

The project combines digital interface design, interaction
design, front-end development, and operational problem-solving.

All inventory records are fictional.

## 2. Product Design Objective

The design objective was to create an interface that supports
a connected inventory exception management workflow.

The prototype enables users to:

- View inventory exception summaries.
- Identify unresolved and high-priority issues.
- Search and filter inventory discrepancy records.
- Review detailed discrepancy information.
- Record investigation notes.
- Update issue resolution statuses.
- Verify changes through the dashboard.

The product is a conceptual demonstration, not a deployed
enterprise inventory management system.

## 3. Evaluation Approach

The product was evaluated independently through functional
checks and selected usability heuristics.

The evaluation focused on:

- Visibility of system status
- Error prevention
- Preservation of user work
- User control
- Consistency
- Functional reliability

No external usability participants were involved.

The findings do not represent validated user preferences
or measured improvements in task completion efficiency.

## 4. Version 1 Functional Evaluation

### Existing Features

SupplySight Version 1 provided:

- Operations Overview
- Exception Management
- Search functionality
- Priority and status filters
- Discrepancy details
- Investigation notes
- Status updates
- Responsive interface layouts

The designer reported that the primary interactions
functioned correctly.

### Finding 1: Error Prevention

**Test Performed**

Attempted to mark an unresolved inventory exception
as Resolved without documenting an investigation note.

**Observed Result**

The application prevented the action and displayed
a message requiring an investigation note.

**Result: PASS**

**Design Principle**

Error prevention.

**Design Decision**

Retain the safeguard.

Requiring documentation helps maintain a structured
resolution workflow and discourages undocumented actions.

### Finding 2: Investigation Notes Lost After Refresh

**Test Performed**

1. Opened an unresolved exception.
2. Entered and saved an investigation note.
3. Refreshed the browser.
4. Returned to the same exception.
5. Reviewed Investigation History.

**Observed Result**

The saved investigation note disappeared after
the browser refreshed.

**Result: ISSUE IDENTIFIED**

**Design Principle**

Preservation of user work and error prevention.

**Impact**

A user could document an investigation and lose
the information unexpectedly after refreshing.

This finding demonstrated a limitation in how
Version 1 managed application state.

## 5. Root Cause

Version 1 stored investigation notes and issue statuses
in JavaScript application memory.

The original sample records were restored when
the page loaded again.

Consequently, user-entered changes were not retained
between page refreshes.

## 6. Version 2 Design Decisions

### Improvement 1: Persistent Investigation Notes

**Problem**

Investigation notes disappeared when the page refreshed.

**Solution**

Implemented browser localStorage to retain changes
to the fictional demonstration records.

**Design Rationale**

Preserving user-entered information helps reduce
unexpected data loss during a demonstration.

### Improvement 2: Persistent Issue Statuses

**Problem**

The original implementation did not retain updated
exception statuses after reloading.

**Solution**

Stored updated issue statuses alongside investigation
notes in localStorage.

**Design Rationale**

Maintaining status consistency supports continuity
when returning to a previously investigated issue.

### Improvement 3: Reset Demo

**Design Opportunity**

Persistent sample records require a way to restore
the original demonstration state.

**Solution**

Added a Reset Demo control with a confirmation dialog.

**Design Rationale**

Reviewers can explore the application, make changes,
and restore the original fictional records.

The confirmation step reduces the risk of accidental
loss of saved demo changes.

### Improvement 4: Storage Transparency

**Design Opportunity**

Users should understand whether their changes
are temporary or retained.

**Solution**

Added a visible browser-storage message and an
explanation that data is stored locally.

**Design Rationale**

Clear system communication helps users understand
the scope and limitations of saved information.

## 7. Version 2 Verification Results

### Test 1: Investigation Note Persistence

**Procedure**

1. Opened an unresolved exception.
2. Entered and saved an investigation note.
3. Refreshed the browser.
4. Returned to the same exception.
5. Checked Investigation History.

**Observed Result**

The investigation note remained available
after refreshing.

**Status: PASS**

### Test 2: Issue Status Persistence

**Procedure**

1. Opened exception EX-1042.
2. Documented an investigation action.
3. Changed its status to Resolved.
4. Refreshed the browser.
5. Reopened EX-1042.

**Observed Result**

EX-1042 remained Resolved after refreshing.

**Status: PASS**

### Test 3: Reset Demo

**Procedure**

1. Selected Reset Demo.
2. Confirmed the reset action.
3. Reviewed the restored sample records.

**Observed Result**

Reset Demo restored the original fictional records.

**Status: PASS**

## 8. Version Comparison

| Feature | Version 1 | Version 2 |
|---|---|---|
| Search and filtering | Implemented | Retained |
| Investigation notes | Session-only | Browser persistence |
| Resolution statuses | Session-only | Browser persistence |
| Required investigation note | Implemented | Retained |
| Reset Demo | Not available | Implemented |
| Storage explanation | Limited | Added |

## 9. Accessibility Considerations

The product includes:

- Semantic interface elements
- Labeled form controls
- Keyboard-focus styling
- Text-based priority and status indicators
- Status announcements
- Responsive layouts

These features were included in the implementation.

A complete WCAG 2.2 conformance audit has not been
performed or documented.

Additional testing is recommended for:

- Keyboard navigation
- Screen reader behavior
- Color contrast
- Mobile interaction
- Focus management

No accessibility conformance certification is claimed.

## 10. Design Outcome

The Version 2 evaluation confirmed that:

1. Investigation notes remain after browser refresh.
2. Updated resolution statuses remain after refresh.
3. Reset Demo restores the original sample records.

The revision addressed the observed loss-of-data
problem and introduced greater control over
the demonstration state.

The results establish functional improvements
within the prototype.

They do not establish measured improvements in
real-world productivity or usability.

## 11. Lessons Learned

The project reinforced the importance of considering
what happens after users complete an action.

A functional interface must communicate outcomes,
protect entered information, and provide predictable
behavior when users return to a task.

The difference between Versions 1 and 2 demonstrates
how evaluating an implemented design can reveal
opportunities for meaningful improvements.

## 12. Project Limitations

SupplySight is independently designed and developed.

- All inventory records are fictional.
- The application is not connected to a database.
- Browser storage is local to the user's device.
- Data is not synchronized across devices.
- The prototype does not provide enterprise authentication.
- No external user research was conducted.
- No formal usability study was performed.
- No production performance gains are claimed.

The application demonstrates a product concept and
working front-end interactions, not a production
inventory management system.

## 13. Future Opportunities

Potential future enhancements include:

- Expanded exception filtering
- Additional workflow feedback
- Improved focus management
- Further accessibility evaluation
- User testing with inventory professionals
- More advanced investigation history
- Backend integration and role-based permissions

These are potential future improvements and are not
represented as completed features.
