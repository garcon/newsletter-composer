# Publication Date

Use this shared publication-date inference for workflows that need an expected issue date, such as Articles, Events, and Anniversary.

## Inference Order

1. Use a publication date explicitly provided by the user.
2. Use the issue folder note front matter date, normally `published`, when present.
3. Use another clearly named issue date in the issue folder note or issue template when present.
4. Otherwise assume the newsletter will be published on the nearest upcoming Monday.

## Monday Rule

If today is Monday and no other date is provided, treat today as the nearest upcoming Monday.

Use the local workflow timezone, Europe/Prague, unless the user or source material explicitly specifies another timezone.

## Date Ranges

When a workflow selects content since a previous newsletter, use this interval unless the skill says otherwise:

```text
(previous_issue_published, current_issue_published]
```

That means content published after the previous issue date and on or before the current issue date.
