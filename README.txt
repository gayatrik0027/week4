# Student Leave Request — Camunda 8

## Files
- `student-leave.bpmn` — executable BPMN process, process ID `student-leave`
- `fa-approval.form` — Camunda Form with required fields and keys `Name`, `Date`, and `Reason`

## How the form is linked
The user task `Submit student leave request` references the deployed form ID `fa-approval-form` through:
`camunda-forms:bpmn:fa-approval-form`

The task is assigned to `student` as a simple starter assignment. In Tasklist, you may need to claim the task or adjust/remove the assignee in Modeler depending on your user setup.

## Deploy and test (Camunda 8)
1. Open `student-leave.bpmn` in Camunda Desktop Modeler.
2. Open `fa-approval.form` in Modeler and confirm the three fields appear. Keep the form ID as `fa-approval-form`.
3. Deploy BOTH files to the same Camunda 8 cluster/environment. The BPMN form key expects the form to be deployed under that ID.
4. Start a process instance for `student-leave`.
5. Open Tasklist, find `Submit student leave request`, claim it if available, enter Student Name, Leave Date, and Reason, then complete the task.
6. Open Operate, select the process instance, and inspect Variables. You should see `Name`, `Date`, and `Reason` with the submitted values.

## Notes
- Camunda 8 UI labels can vary slightly by version.
- This is a deliberately simple submit-and-finish workflow, suitable for demonstrating form submission and process variables. It does not include a separate faculty approval task.
- If your environment uses a different Camunda 8 minor version, open and validate the files in the matching Desktop Modeler before deployment.
