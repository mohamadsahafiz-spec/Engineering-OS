# Prompt Enhancement Principle 01

## Never Write the Minimum Prompt

A prompt should not merely describe the desired outcome.

A prompt should engineer the desired outcome.

---

## Enhancement Mindset

# Atlas Rule

Never send the first version of a prompt.

Always perform one enhancement pass before presenting it.

During enhancement, look for:

• ambiguity
• loopholes
• assumptions
• shortcuts
• missing acceptance criteria
• missing failure criteria
• missing verification
• unnecessary complexity

Only then present the prompt.

Before finalizing any prompt, perform an enhancement pass.

Ask:

• Is there ambiguity?
• Can the AI satisfy this incorrectly?
• What assumptions might it make?
• What shortcuts could it take?
• How would I verify success?
• Can acceptance criteria be made observable?
• Can failure conditions be explicitly defined?
• Can unintended behavior be prevented?

Only after this review should the prompt be considered complete.

---

## Engineering Rule

An enhanced prompt is always preferred over a minimal prompt.

The goal is not shorter prompts.

The goal is predictable results.

---

## Enhancement Hierarchy

Level 1
Objective

Level 2
Requirements

Level 3
Constraints

Level 4
Observable Acceptance Criteria

Level 5
Failure Conditions

Level 6
Verification Steps

Level 7
Expected Reply Format

A prompt should progress through each level whenever appropriate.

---

## Golden Rule

Every enhanced prompt should reduce interpretation and increase predictability.

The AI should know exactly:

• what to do,
• what NOT to do,
• how success is measured,
• how failure is detected,
• and what evidence proves completion.

---

## Example

Weak Prompt

"Create the missing files."

Enhanced Prompt

"Physically create each missing Markdown file inside the repository. Each file must appear in File Explorer, open successfully when clicked, contain a placeholder title, and remain visible after reopening the project. Editing README alone does not satisfy this requirement. If any file is absent from File Explorer, the task is considered incomplete."