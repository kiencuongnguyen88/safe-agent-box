# First Safe Agent Box Readback Example

Status: example / documentation only

This example shows one small Safe Agent Box loop for a Codex-style pull request review.

It is not a runtime enforcement system, sandbox, security guarantee, or production automation.

---

## Scenario

A maintainer wants an AI coding agent to review a documentation pull request before merge.

The maintainer does not want the agent to edit files directly or run commands. The first run should be review-only.

---

## 1. Box

```yaml
safe_agent_box:
  task: review_one_pull_request
  mode: read_only_review
  repository_scope:
    include:
      - README.md
      - docs/
      - prompts/
      - templates/
    exclude:
      - private notes
      - local credentials
      - deployment settings
  allowed_actions:
    - inspect the diff
    - identify unclear wording
    - suggest review comments
    - propose a follow-up patch plan
  blocked_actions:
    - edit files directly
    - merge the pull request
    - publish a release
    - change repository settings
    - run deployment commands
  human_gate_required_for:
    - applying a patch
    - approving the pull request
    - merging
    - publishing release notes
```

---

## 2. Action plan

Before acting, the agent should state:

```text
I will review the PR as documentation only.
I will not modify files.
I will report unclear wording, missing boundary statements, and any follow-up patch ideas.
I will stop before any write action.
```

---

## 3. Example review output

```yaml
review_summary:
  verdict: needs_small_follow_up
  files_reviewed:
    - README.md
    - docs/maintainer-workflow.md
  findings:
    - README explains the core idea clearly.
    - The Human Gate boundary could be repeated near the quick-start path.
    - The readback section should show files touched, risks, and next checkpoint.
  suggested_follow_up:
    - Add one compact readback example to docs.
    - Keep the wording as method guidance, not runtime enforcement.
```

---

## 4. Readback

After the review, the agent should produce a short readback:

```yaml
readback:
  task: review_one_pull_request
  mode: read_only_review
  files_changed: none
  commands_run: none
  repo_settings_changed: false
  merge_or_release_action: false
  risks_found:
    - wording could imply stronger enforcement than intended
  recommended_next_step:
    - maintainer decides whether to open a documentation-only follow-up PR
  human_gate_status:
    required_before_apply: true
```

---

## 5. Maintainer decision

The maintainer can then choose one of three paths:

```yaml
maintainer_options:
  accept_no_change:
    meaning: no patch is needed
  request_patch_plan:
    meaning: ask for a patch proposal but still do not apply automatically
  approve_doc_patch:
    meaning: open a separate documentation PR after Human Gate
```

---

## 6. Boundary reminder

Safe Agent Box helps make the operating boundary visible.

It does not replace maintainer judgment.

Core line:

```text
Box first.
Run second.
Readback before trust.
```
