
Jira cli wrapper
==============

This wrapper provides a git-like experience for using jira from the command line.

Example
-------------
Create a new jira
```
jira create -m 'this is a new new ticket description' 'summary of ticket'
```

Comment on a jira
```
jira comment -m 'this is a short comment' JIRA-123
```
Log time against a jira
```
jira time JIRA-123 15m
```
Move a jira to a transition state
```
jira move close JIRA-123
```

Password Requirements
--------------

You must setup your jira password:
Even if you normally log in to JIRA using google authentication,
you will need to have a basic Atlassian ondemand password set up.
This is separate from your google credential and does not impact it.
https://confluence.atlassian.com/display/AOD/Changing+Your+Password+in+Atlassian+OnDemand


Required Gems
--------------
- thor
- colorize

Required Software
--------------
bob swifts java jira cli tool.

https://marketplace.atlassian.com/plugins/org.swift.jira.cli


Setup
--------------

jira config will print a default config file to modify

``` 
./jira config > ~/.jira.yaml
```

Modify ~/.jira.yaml with your settings.
jira_jar should be set to the jar file location downloaded from the bob swift cli site.

Transitions Setup
--------------

This section is for defining how to move issues to different state, you identify a final_state and which intrim states get there
For example with the default jira workflow:
```
 transitions:
  close:
    final_state: 6      # Id of the final state we want to get to
    intrim_state:
      - 2
    resolution: Fixed
```

