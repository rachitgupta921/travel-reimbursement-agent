# travel-reimbursement-agent

Travel Reimbursement Approval Agent

Overview

This project is a Python-based Travel Reimbursement Approval Agent developed for the AI Developer Candidate Assignment.
The notebook evaluates employee travel reimbursement claims against the travel reimbursement policy provided in the assignment.
The system checks:

- Expense category eligibility
- Receipt requirements
- Meal, lodging and ground transport limits
- Airfare class
- Approval thresholds
- Submission timing
- 
It returns one of four decisions:

- APPROVE
- PARTIAL_APPROVE
- REJECT
- MANUAL_REVIEW
- 
Project Structure

travel-reimbursement-agent/
│
├── YourName.ipynb
└── README.md

Rachit_Gupta_travel_reimbursement_agent.ipynb is the main notebook and contains the complete implementation.

How to Run

Open the notebook using Jupyter Notebook, JupyterLab, Google Colab, or VS Code.
Run the notebook cells from top to bottom.
Install the required Python packages if they are not already installed:
pip install pandas matplotlib openai
The notebook can also run without an API key using the local policy-checking workflow.

Main Checks

The notebook uses separate functions for:

1. Policy lookup
2. Receipt checking
3. Category limit checking
4. Approval threshold checking
   
These checks are combined to determine the final result for each claim.
Policy Rules

The implementation uses the policy rules supplied with the assignment, including:
- Meals: maximum $75/day
- Lodging: maximum $200/night
- Ground transport: maximum $50/day
- Economy airfare is reimbursable
- Business/first-class airfare requires manual review
- Required receipts must be attached
- Claims above $2,000 require manual review
- Claims submitted more than 30 days after the expense date require manual review
  
Sample Claims

The notebook evaluates all five claims provided in the assignment:
- CLM-001
- CLM-002
- CLM-003
- CLM-004
- CLM-005
  
Output

The final notebook cell produces a JSON array containing the result for each claim.
Each result contains:
claim_id
decision
approved_amount
deducted_amount
missing_docs
policy_refs
confidence
explanation
tools_used

Dashboard

The notebook includes a small dashboard showing the decision breakdown and approved versus deducted amounts based on the actual claim results.
Notes

The implementation keeps the policy checks separate so that the decision for each claim can be inspected and explained.
Cases involving missing required receipts, business/first-class airfare, late submission, or amounts above the approval limit are sent for manual review rather than being automatically approved or rejected.
