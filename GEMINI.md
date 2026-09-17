# Repository Rules: Verification Before Staging & Committing

<RULE>
**CRITICAL RULE: Mandatory Error & Diagnostic Inspection Prior to Commit**

Under NO circumstances may you stage (`git add`), commit (`git commit`), or push (`git push`) code changes without first checking for lint warnings, syntax errors, and language-server/IDE diagnostics on all touched files.

### The Protocol:
1. **Save & Inspect:** After modifying any file, immediately inspect the file's problems and diagnostics (e.g., via editor diagnostics or linters).
2. **Zero Errors & Warnings:** Resolve all reported compiler errors, syntax issues, and compatibility/lint warnings prior to staging files.
3. **Film Review Audit:** Verify that no regressions or unaddressed diagnostics exist before issuing any `git commit` or `git push` commands.
</RULE>
