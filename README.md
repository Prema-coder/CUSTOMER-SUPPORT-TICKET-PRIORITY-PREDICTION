# CUSTOMER-SUPPORT-TICKET-PRIORITY-PREDICTION

Support Ticket Intelligence Agentforce Project
Project Overview

Support Ticket Intelligence is an Agentforce-based Salesforce solution that automatically analyzes customer support tickets, determines ticket priority, and provides recommendations for handling support requests.

The solution uses:

Salesforce Custom Object
Salesforce Flow (Autolaunched Flow)
Agentforce Agent Action
Agentforce Subagent
Custom Topic Configuration

The agent collects an Account Name, retrieves the latest support ticket, analyzes the ticket content, determines its priority level, and returns the result to the user. Agentforce actions can call Flows and use inputs and outputs to interact with Salesforce data.

Features
Priority Classification
High Priority

Keywords:

urgent
not working
failure
critical

Action:

Recommend immediate handling
Escalate to senior support staff
Medium Priority

Keywords:

issue
slow
delay

Action:

Assign to standard support queue
Low Priority

All other tickets

Action:

Normal processing
Components Used
1. Custom Object

Support Ticket Intelligence

Fields:

Field Name	Type
Ticket Number	Auto Number
Customer	Lookup(Account)
Contact	Lookup(Contact)
Issue Type	Picklist
Description	Long Text
Priority	Picklist
2. Autolaunched Flow

Flow Name:

Support_Ticket_Intellegence

Input Variable:

varAccountName

Properties:

Data Type = Text
Available for Input = True

Output Variable:

varActionMessage

Properties:

Data Type = Text
Available for Output = True

The Flow receives an account name, performs ticket analysis logic, and returns a response message. Agentforce supports Flow-based actions using Autolaunched Flows with defined input and output variables.

3. Agent Action

Agent Action Label:

Support_Ticket_Intellegence

Description:

Analyzes support tickets, determines priority level,
assigns support agents, and creates tasks for
high-priority tickets.

Loading Text:

Analyzing support ticket...

Output:

varActionMessage

Output Rendering:

Text

Agentforce actions can invoke Flows and return outputs back to the conversation.

4. Agentforce Subagent

Subagent Name:

Support Ticket Intelligence Assistant

Purpose:

Analyze support tickets
Determine ticket priority
Provide recommendations
Guide users through the ticket analysis process
Agent Instructions
You are a Support Ticket Intelligence Assistant.

Your role is to analyze customer support tickets and determine their priority level.

Instructions:

1. Ask for the Account Name if not provided.
2. Use the Support_Ticket_Intellegence action whenever a user requests ticket analysis.
3. Retrieve the latest support ticket associated with the account.
4. Determine ticket priority.

High Priority:
- urgent
- not working
- failure
- critical

Medium Priority:
- issue
- slow
- delay

Low Priority:
- all other cases

5. Recommend immediate escalation for high-priority tickets.
6. Display the action output.
7. Remain concise and professional.
8. Do not expose Salesforce record IDs.
9. Inform users if no ticket is found.
10. Guide users through the ticket analysis process.
Testing
Test Case 1

Input:

Analyze support ticket for ABC Company

Expected Output:

Retrieving latest support ticket for ABC Company.

Priority: High
Recommendation: Escalate immediately to senior support staff.
Test Case 2

Input:

Check ticket priority for XYZ Company

Expected Output:

Priority: Medium
Recommendation: Standard support handling.
Flow Activation

Steps:

Open Setup
Search Flows
Open Support_Ticket_Intellegence
Verify:
Active Version = 1
Status = Active
Save
Activate
Agent Activation

Steps:

Setup → Agentforce
Open Agent Builder
Open Support Ticket Intelligence Subagent
Add Agent Action
Save
Activate Agent
Technologies Used
Salesforce Developer Edition
Agentforce
Salesforce Flow Builder
Salesforce Custom Objects
Agent Actions
Agentforce Subagents


Outcome:

The Support Ticket Intelligence solution enables automated support-ticket prioritization using Salesforce Agentforce. It improves support efficiency by identifying urgent issues, recommending escalation paths, and assisting support teams with faster response times. Agentforce can use Flow-based actions to execute business logic and return results directly within conversations.


Deploy link : https://drive.google.com/file/d/1VrY9XkMxWB1nVeKYRyEm3ZOW7AWTqqGy/view?usp=sharing
