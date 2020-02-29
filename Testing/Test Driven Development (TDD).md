# Test Driven Development

The TDD workflow starts with th product manager gathering business requirements form the business stakeholders, and the liaising with the technical team to refine these requirements, taking into account feasibility, cost, and time constraints. 

The scope of the requirements should be small. If the application is large, the product manager should prioritize the requirements by importance and urgency, and group them into phases. 

These requirements should be well-defined and unambiguous, so that there is no room for (mis)interpretation.  This means they should quantified as much as possible.

## E2E tests with Cucumber

Cucumber is an automated test runner that executes tests written in a **Domain-Specific Language (DLS)** called **Gherkin**. This language allows us to write tests in plain language, usually in a behavior-driven way.

### Features, scenarios, and steps

To use Cucumber, you'd first separate your platform into multiples features; then,  within each feature, you'd define scenarios to test for. 

Each feature should be defined, using the Gherkin language, within its own `.feature` file.

#### Gherkin keywords 

In Gherkin, every non-empty line starts with a Gherkin keyword (although there are several common exceptions). 

- `Feature`: Specifies the name and description of the feature. A feature is just a way to group related scenarios together.

- `Scenario`: Specifies the name and description of the scenario.

- `Given`, `When`, `Then`, `And`, `But`: Each scenario is made up of one or more steps, each corresponding to a JavaScript function that is to be executed by Cucumber. 

- `Background`: Allows you the set up a common environment to execute all your scenarios.

- `Scenario Outline`: Allows you to define a template for multiple scenarios that differ only in certain values. 

- `Examples`: When using scenarios outline, the `Examples` keyword allows you yo specify values to plug into the scenario outline.

- `"""`: Allows you to use doc strings to specify multiple string as parameters.

- `|`: Allows you yo specify more complex data tables as parameters.

- `@`: Allows you to group related scenarios together using tags. 

- `#`: Allows you to specify comments, which will not be executed by Cucumber.

  