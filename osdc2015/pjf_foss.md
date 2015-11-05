# Bulding Healthy Open Source Communties... in Space!

@pjf, OSDC 2015

Slides: https://github.com/pjf/healthy-communities

Original title: "To the moon: FOSS lessons from building CKAN"

Assumptions on talk
 * you have code in your project
 * you want to attract contributors
 * you want to retain contributors
 * you want your project to succeed (different to *you* succeeding)

The thing that can get in the way of successful open source projects is ego

Not a complete list. Use your best judgement. 

---

Releasing code is scary. 
 * 'People might judge me on my code!'
 * Admitting that your code is wrong is hard
 
Accepting code you don't like is scary
 * easy to be overcontrolling
 
Simple rule to accepting contributions: Is it better than what it was before
 * including technical debt
 * even if you then go back and fix the tabs, spaces, styling. 
 
KSP-CKAN - Kerbal Space Program - Comprehensive Kerbal Archive Network 
 * mod mananger for Kerbal Space Program
 * apt-get for KSP 
 * almost a year old
 * > 200 contributors (via git log --short -sn)
 * > 32,000 active users
 * metric - decades of human joy delivered

GitHub
 * README.md - rendered on project page
 * CONTRIBUTING.md - rendered on new Issue and Pull Request pages
 * Use an Organisation - share the administrative load
 

Fix problems *before* you start
 * how do we do versioning, releasing.. 
 * how do we handle inappropriate behaviour?
 
> "The moment I hear that you need a 'thick skin' to contribute [in a community], I think your community is toxic. " - pjf
 
It's hard to change an existing community, get it right from the start

Code of Conduct
 * clearly define expectations, what is allowed, not allowed
 * e.g. Rust lang - in this project, swearing is ok, swearing at people is not
 * safety of contributors
 * tend to attract better contributors
 
Like a licence, don't write your own
Put it in your IRC Topic, or other central locations
 
Citizen Code of Conduct.org
 * CC template, insert your name here

CONTRIBUTING.md sample content
 - CoC stub
 - Reporting bugs and opernign issues
 - code and contributions
 - 
 
When inducting a new contributor - introduce CoC, and ensure they know they can enforce it. 
 - doesn't rely on the head of the org to handle

Have a Licence!!
 - choose a license .com
 - put it in LICENCE.md
 - require contributors to also use that licence
 - stub into CONTRIBUTING.md

Don't exclude contributors by accident 
 - e.g. weekly public video conferences
 - pros: face to face conversations, archived for later
 - cons: primary way where decisions were made
 - time, timezone issues - people who aren't awake can't help make decisions
 - exscludes anyone with hearing difficulties
 - excludes coffeeshop contributors - unable to contribute vocally
 - excludes people who were victims of internet harassment - actively dangerous
 - unaware of who's being excluded
 - homogenerity inertia - read the essay

Solutions: 
 - start with diverse leadership; race, gender, OS, etc
 - outreach - find people who are not like yourself
 - outreachy, openhatch
 
Don't stand in the way of creativity
 
First timers? Welcome them!
 - "Hi! Here's some resources, guideline, etc" 
 - Possibly have a bot - rust has a 'highfive' bot - walks through process, and alerts senior member
 - lead by example - more likely to welcome others

Give people the permissions to do their job 
 - most serious contributors are competent
 - have an induction process e.g. 'flat structure, do what you feel comfortable with. Have another human go over some code
 
Encourage helping others 
 - allow others the right to do code review and merging
 
Encourage decision making 
 - don't be a bottle neck, distribute leadership
 
Robust development process
 - git -> easier rollbacks

Continuous integration 
 - multiple versions, operating environments
 - robots :D, e.g. Travis-CI

Pull Requests + Code Review
 - human review, even if it's a core contributor
 - amazing way to learn, can be distrubed

Automated releases 
 - don't rely on a single human
 - protects from potential harm
 - check the KSP-CKAN .travis.yaml file for examples
 
Have entry level tasks!
 - does not have to be code!
 - support - Q&A
 - classifying new issues
 - sharing experiences, user stories
 - writing documentation
 - newbies are awesome, they see the rough edges, the barriers

Invite and empower people to contribute 
 - "Can we get this thing happening?" "Sure, if you feel comfortable, here's the instructions"
 - Not, "Patches welcome", it's "Here's how you can do it, if not, i'll help you do it"
 
Recognise non-code contributors: 
 - people who report problems 
 - e.g. 'grr, bug report' -> 'yay! bugs!' 
 - acknowledge bugs!
 - thank the people who interact in good ways
 
Community Manangers are amazing!
 - pjf would rather have a good community manager than a good coder

Octohat
 - run through github, and shows non-code contributors

Advance the status of others
 - 'here's the list of people who are awesome who helped with this release'

`#LABHR`
 - don't just keep the thanks within the project 
 - LinkedIn :D

KSP-CKAN has got people jobs
 - lost contributors because they got their dreamjob
 - people have headhunted via CKAN

Open Source contributors advance people's professional careers
 
Don't be a single person who knows everything 
 - admit that you might need help 
 - all pjf's contributors knew more than he did (first c# project)
 - take their advice
 - learn from them
 - remind others that you might be wrong
 - empower others to take leadership

Loomio
 - consensis based decision making
 - open source app

Do not beat yourself up. 
 - it will be more than a full time job 
 - you will make mistakes
 - you will need a break 
 - you will let other people down
 - you will be criticised
 - **it's okay**. 
 - it's ok to take time out
 - it's ok to take a break 
 - a healthy community can continue without you



