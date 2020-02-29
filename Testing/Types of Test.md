# Types of Test

## Unit tests

These test the smallest testable part of an application, called **unit**. With unit test, we are only concerned with the function of the unit, **independent of external dependencies**. Unit tests test a small and specific component of the whole code base, using minimal (or no) dependencies, and without calling other parts of the application (that is, the are no side-effects).

## Integration tests

These test whether different units can work together as a single, larger ensemble. Integration tests test the integration between two or more units and unsure the are compatible. 

## E2E/functional tests

These test the flow of an application from start to finish, acting as if we are the end consumers. 

## User Interface (UI) tests

UI tests are automated tests that mimic the behavior of real users interaction with the UI, such as scrolling and clicking. 

## Manual tests

These are test that cannot be automated. Manual tests should be kept to a minimum as they are not deterministic and there's a high cost to running them.

## Acceptance tests

These tests are most focused on business needs. They are a list of business requirements (as opposed to functional requirements), laid out by the business stakeholders, that the platform must fulfill. For example, one such requirement might read "95% of all visitors must be able to load the page within 3 seconds". Pats of the acceptance test may be written in a **Behavior-Driven Development (BDD)** format, which focuses on the steps that an actual user may take when interacting with the platform. 