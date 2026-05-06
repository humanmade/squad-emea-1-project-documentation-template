# Definition of done

A ticket is considered **Done** when all of the following criteria are met.

## 1. Functional completeness

- All acceptance criteria on the ticket are met as written.
- The functionality works as described for the agreed user journeys only.
- Behaviour matches the existing site unless explicitly stated otherwise in the ticket.

No additional behaviours, edge cases, or enhancements are assumed beyond what is written.

## 2. Browser & device support

Works correctly across the browsers and devices defined in [Testing — Browser & device coverage](../Testing.md#browser--device-coverage).

If an issue occurs outside those constraints, it is out of scope unless added as a new ticket.

## 3. Responsiveness & visual fidelity

- Layout is visually consistent with the agreed designs or existing site patterns, within agreed tolerances.

## 4. Performance

Have taken reasonable tests to test the performance of the work. It's not always possible to test performance on staging environments accurately.

For more information, refer to performance criteria defined in [Testing — Performance](../Testing.md#performance).

## 5. Accessibility

Meets the accessibility criteria defined in [Testing — Accessibility](../Testing.md#accessibility).

## 6. Testing & validation

- Tested by engineers on staging against the above criteria.
- Deployed to staging and available for review by product owner.
- A ticket enters Client Review once it meets this Definition of Done.

## 7. Feedback & rework

- One round of client feedback is included per ticket.
- Feedback must relate to:
    - Acceptance criteria not met, or
    - A clear defect against the Definition of Done.
- Requests for additional functionality, alternative behaviour, or expanded scope will be logged as new tickets or change requests.

## 8. Regressions & edge cases

- Regressions caused directly by the ticket work will be fixed within scope.
- New edge cases or uncovered scenarios are out of scope unless defined in the original ticket.

## 9. Final completion

A ticket is Done when:

- It meets this Definition of Done
- It has passed one client review cycle or no feedback is received within the agreed review window
- It is approved or implicitly accepted
