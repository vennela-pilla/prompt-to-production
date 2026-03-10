skills:
  - name: extract_leave_policy
    description: Extract relevant leave policy rules from the HR policy document.
    input: HR policy document text (string) loaded from policy_hr_leave.txt.
    output: Structured summary containing leave types, eligibility conditions, and leave limits.
    error_handling: If the document does not contain recognizable leave policy rules, return "NOT_FOUND" and flag NEEDS_REVIEW.

  - name: answer_leave_query
    description: Answer an employee question using only the HR policy rules extracted from the document.
    input: Employee question (string) and extracted leave policy rules (structured text).
    output: A concise answer that references the policy rule supporting the response.
    error_handling: If the question cannot be answered using the policy document, return "INSUFFICIENT_POLICY_INFORMATION" and flag NEEDS_REVIEW.