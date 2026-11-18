# Agentic SDLC — URL Shortener Prototype

A working  prototype demonstrating:

- Requirement understanding and clarification.
- Planning and human approval.
- Code generation and automated testing in Docker.
- Documentation and separately approved local deployment.
- Greenfield, brownfield and ambiguous requirement scenarios.
- Workflow controls, evaluations and run measurements.

The release ZIP contains the full agent source, evaluation code, application examples, tests, evidence and detailed instructions.

## 1. Download

**[Download Schwab-Submission.zip](https://github.com/raamkrishnet/agentic-sdlc-url-shortener/releases/download/v1.0-review/Schwab-Submission.zip)**

Save the file as `Schwab-Submission.zip` in your Downloads folder.

Download the named ZIP attachment under the release’s **Assets**.

## 2. Install

The tested reviewer environment is Windows with PowerShell, Python 3.12 and Docker Desktop using Linux containers. Internet access is required for setup.

Open PowerShell and run each command separately:

```powershell
Expand-Archive -LiteralPath "$env:USERPROFILE\Downloads\Schwab-Submission.zip" -DestinationPath "$env:USERPROFILE\Documents\SchwabReview"
```

Use a fresh destination folder.

```powershell
Set-Location "$env:USERPROFILE\Documents\SchwabReview\Schwab-Reviewer"
```

```powershell
.\Setup.ps1
```

Setup assists with missing prerequisites. After installing Docker Desktop, open it, complete its first-start prompts and wait for the engine to run. Rerun setup if necessary.

Continue after **Setup complete** appears.

## 3. Follow the complete live walkthrough

Open the packaged instructions:

```powershell
notepad .\README.md
```

Follow their examples in order:

| Scenario | Example |
|---|---|
| Greenfield | Generate, test and start a new URL-shortener service. |
| Brownfield | Add an `X-Service-Name` health-response header while preserving existing tests. |
| Ambiguous | Request an environment header, clarify its value, then implement and test it. |

Start the live agent:

```powershell
.\RunAgent.ps1
```

The packaged README gives the exact requirement text, prompt answers, approvals, ports and HTTP verification commands for every scenario.

Use `gpt-5.2` when prompted for the model, provided your account supports it.

Live planning and generation require your own OpenAI API key and API credits. At the Planner menu, choose `credentials`, then use the clipboard key-entry method. No API key is included in this repository or ZIP.

Use two PowerShell windows: one for the agent and another for service checks.

## 4. Optional checks without OpenAI calls

Run the supplied application and workflow checks:

```powershell
.\Test-Prototype.ps1
```

Run control evaluations:

```powershell
.\Evaluate.ps1
```

Evaluate the recorded QA suite against planted defects:

```powershell
.\Evaluate.ps1 -Mode Mutation -AllowIsolatedTests
```

These commands make no OpenAI calls. Docker is required for application and planted-defect testing.

The optional Judge requires separate paid-call authorization. See the packaged `docs/EVALUATION.md`.

## 5. Understand the package

Read `FILE_GUIDE.md` inside the extracted package for plain-language explanations of folders, commands, agent modules, generated applications, tests and reports.

New engineering outputs appear under:

```text
runtime/agent-sessions/<session-id>/
```

New evaluation scorecards appear under:

```text
runtime/evaluations/<evaluation-id>/
```

## Scope and limitations

This is a bounded local prototype with documented validation and test-coverage limitations. Review the packaged requirements tracker and evaluation guide. Passing generated tests is not complete correctness assurance.

Deployment means starting an approved service locally in Docker. Production hosting, enterprise audit identity and deployed database rollback are outside this submission’s scope.

## Package integrity

SHA-256 of the reviewed release ZIP:

```text
5d9f2ca643e2728b4db11cc457eb28f7f23048e7bf6f7cf60eaad1fabe2b8123
```
