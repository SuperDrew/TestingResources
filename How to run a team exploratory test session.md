# How to Run a Team Exploratory Test Session

- Do you have an explicit charter for the Team Exploratory Testing Session? If you don't go and create one, if you aren't able to come up with a charter seriously consider whether you need a Team Exploratory Testing Session.
- If you are getting help from people outside your team, notify them clearly about what is happening well in advance. It is helpful to include testers from outside the team if you are short on them.  This message should include the charter, clearly explaining what the objective of a testing session would be and the fact that we are specifically doing *exploratory* testing. This should prevent people from entering the session with an unrealistic idea of what is expected of them.
-	With the help of any testers that agreed to help, perform the exploratory test session as follows:
    - Set up test resources and environments needed for the session (e.g. databases prepopulated, application versions known).  This should be based on your understanding of what users most commonly use, for example if you're testing a web app and 90% of your users use Chrome, then most of your testing should be on Chrome.
    - Developers pair up (preferably with a tester) for the session.
    -	The whiteboard could contain the following things:
        -	Charter: the objective of the test session; what is it trying to achieve?
	      - Relevant use cases: these may be specific parts of the product, versions of relevant dependencies/OSs etc... These help guide the testing pairs during the session.
        -	Personas/stakeholders to consider: optional, but could be useful to dissect more general changes that affected a wide range of customers.
        -	Risks we’re trying to mitigate: these can help focus the session.
        - Application under test candidate build numbers (and links to get the correct versions if applicable).
        -	Last default build number: can be used to check if a bug has been introduced by the new changes rather than it being an existing bug.
        -	Test servers/databases.
    - During the test session, pairs should produce sad/meh/happy stickies for each noteworthy discovery or observation they make, you can use different color stickies for each category.
    -	The session organiser should collect these stickies as the session progresses, grouping them into clusters on the whiteboard as they are collected. This means that everything will be already sorted into clusters by the time everyone gets together to conclude the session. Clusters don’t need to be placed along any dimensions - just group them accord to some meaningful commonality.
    - After the sessions, the team should assess the issues raised and rank them according to severity in terms of how they affect the release and how urgently they need to be attended to.
	- Make actions for the highest priority groups. These may be tasks, stories or bug fixes for the teams board or as topics of discussion for the next retro.
    - Remember to thank the testers for their involvement and credit them in the release email.
