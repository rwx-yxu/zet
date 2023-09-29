# Use directory names to reference composite github actions in workflows

When calling an action as part of workflow, you should reference by directory rather than calling the path the action.yml file itself.

However, if you have a workflow action yml which references another workflow file, you have to put in the pull path to that file.
