# Testing mind-set list
This documents purpose is to assist an individual to perform testing activities.  Reading through it before attempting to test should help approaching testing when coming from a different function.

## Mind-set
- Critical thinking - don't accept, question.  This mind-set is helpful for producing useful questions. Think about what assumptions are behind statements, question them. If you can't think what they are question them.  If somebody makes a bold statement without data backup, question it.  Have a searching mind, don't accept what people say as fact.  Not because "they're wrong" but because exploring what is said and understood can often uncover new information.
- What happens if user does what we don't expect, expect them to do this?  Try to discover unexplored paths through your product.
- You're not building for yourself or for your own understanding.  Remember that your users are not going to use your product the same way you do and probably not in a way you can exactly imagine or describe.
- Risk Framework - view everything in a risk framework: Impact and likelihood
 - Impact:
   - If this happens how will it affect the user?
   - How bad will the effect be?  Will it cost the user money and/or time?
 - Likelihood:
   - What is the chance that this risk will happen?  
   - How often will it happen?
- Evaluate the value of the work to your users, the users' needs/problems and solutions should be at the front of your mind.
- Data trumps opinion.  For example, if you want to develop a particular feature and don't have some user data, whether qualitative or quantitative, question why you are working on that feature.

## Questions
- What is the user story the work affects?
- What context is your user working in?
- What problem is this solving?  Does it solve it?
- Why?
 - Why are we doing this work?
 - Why does the user need this?
 - Why are we doing the work like this? (Have we considered alternatives)
- How?
 - How does this affect the user?
 - How does that work?
- What?
 - What do our users want from this?
 - What over features with this interact with?
- Huh?
 - If you don't understand, don't let it go, ask Huh?

## Specifics
- This section should contain specific known risks you product faces.  It can also contain various test dimensions (dimensions across which your testing should vary).
- E.g.
- OS Version
- Dat input size
- High user concurrency
- Bitness (x86, x64)  
- Heuristics (see below e.g. performance)
- Opportunity cost, test riskiness thing first
- Big input, small input, null

## Cheat Sheet

### Heuristics
A heuristic is a fallible experience-based technique that is useful for problem solving.

`CRUSSPIC STMPL`

|Heuristics			| Description
|---------------| -----------
|Capability			| What can the software do? What should it do?
|Reliability		| How often would this break?
|Usability			| How easy is it to use? Can the user figure out what to do?
|Security			  | If a hacker attempted to get access how easy would it be?
|Scalability		| Does this work for 2 users, 10 users, 50 users?  Think about concurrency and data size.
|Performance		| Will the user notice how long this takes?  How will this scale with multiple users, more blocks, larger dbs, massive migration scripts?
|Installability	| Do files need to be added or removed from the installer?  Does this change dependencies?
|Compatibility	| Does this rely on the windows or a dependencies version?
|Supportability	| How easy will it be to diagnose if something goes wrong?  How is it logged?
|Testability		| How hard is it to setup the environment to test this?  How hard is it to test?
|Maintainability| Is this easy to understand?  Does it create needless complexity in the code?  Will somebody else understand it in 6 months time?  Does it discourage change towards a mess?
|Portability		| Not sure this affects us, does it work on mobile?
|Localizability	| Do you ever do string comparisons?  Or numerical comparisons?  If in doubt run it on a Turkish machine.

#### Extras
|Heuristics			| Description
|---------------| -----------
|Documentation | Is there user documentation explaining how to use the system? Is there help? Are there design/achitecture docs? Readmes? 
|Recoverability | Does the system recover from serious errors gracefully?
|Failover | When the system fails does it fail over to DR? When the main system comes back online can we go back to it?
|Compliance | Does the system comply with all laws and regulatory requirements?

#### Performance
Remember to take business growth into account, you should be able to tell the business when the system will stop meeting requirements at it's current rate of growth. Test both at nominal and at least 2x nominal measured load, this factor is up for debate.

|Heuristics			| Description
|---------------| -----------
|Volume | How does the system handle large volumes of data? Using high volumes of data what happens to the responsiveness of the system
|Stress | Stress the system by limiting the physical assests it has access to, reduce memory, IO, or CPU. If possible find where it stops working
|Load | Emulate different constant loads and measure the systems response times. The load size should be related the business requirements. 
|Ramp | Ramp the load on the system up, measure the response, the max level and rate of increase needs to come from business requirements or measured performance.
|Spike | Does you system need to handle large spikes in load? What does the live performance profile look like? Give the system a spike and measure how long it takes to clear out load.
|Endurance | How long can the system survive at a reasonably high load?

### Oracles
An Oracle is a means to recognise and evaluate problems in software.

Consistency oracles: `PIC UP CHEFS`

|Oracles              |Description
|---------------------|-----------------------------
|Purpose              |Consistent with its purpose, both explicit and implicit.
|Image                |Consistent with an image the company wants to project.
|Comparable Products  |Consistent with other comparable products.
|User Expectations    |Consistent with what the user wants.
|Product              |Each element is consistent with comparable elements in the product.
|Claims               |Consistent with what important people say its supposed to do.
|History              |Consistent with itself over time.
|Explainability       |Consistent with ability to explain it.
|Familiar             |Consistent with pattern of solutions for familiar problems.
|Standards & Statues  |Complies with applicable laws and standards.

Credit: The Heuristics and Oracles above stem from James Bach's work.
