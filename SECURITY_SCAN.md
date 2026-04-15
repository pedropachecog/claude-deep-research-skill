# Security Scan Report: claude-deep-research-skill

**Date:** 2026-04-15  
**Repository:** https://github.com/pedropachecog/claude-deep-research-skill  
**Original:** https://github.com/199-biotechnologies/claude-deep-research-skill  
**Scanner:** Manual code review

---

## Summary

**VERDICT: ✅ SAFE**

No unsafe, immoral, or illegal content found. This is a legitimate research tool for generating citation-backed research reports.

---

## Files Scanned

### Python Scripts (7 files)
| File | Purpose | Status |
|------|---------|--------|
| `research_engine.py` | Research pipeline orchestration | ✅ Clean |
| `validate_report.py` | Report quality validation | ✅ Clean |
| `verify_citations.py` | Citation verification via DOI/URL | ✅ Clean |
| `citation_manager.py` | Citation tracking utilities | ✅ Clean |
| `evidence_store.py` | Evidence persistence | ✅ Clean |
| `extract_claims.py` | Claim extraction from reports | ✅ Clean |
| `md_to_html.py` | Markdown to HTML conversion | ✅ Clean |

### Reference Documentation (5 files)
| File | Purpose | Status |
|------|---------|--------|
| `methodology.md` | 8-phase research methodology | ✅ Clean |
| `report-assembly.md` | Report generation guidelines | ✅ Clean |
| `quality-gates.md` | Quality validation standards | ✅ Clean |
| `html-generation.md` | HTML template instructions | ✅ Clean |
| `continuation.md` | Long report handling | ✅ Clean |

### Templates (2 files)
| File | Purpose | Status |
|------|---------|--------|
| `report_template.md` | Report structure template | ✅ Clean |
| `mckinsey_report_template.html` | HTML styling template | ✅ Clean |

---

## Security Checks Performed

### 1. Dangerous Code Patterns
**Checked for:** `subprocess`, `os.system`, `eval()`, `exec()`, `__import__`, `compile()`

**Result:** ✅ Only `subprocess` in test files (for testing scripts), all `re.compile()` calls are regex patterns

### 2. Network Operations
**Checked for:** `urllib.request.urlopen`, `requests.get/post`, downloads

**Result:** ✅ Only `verify_citations.py` uses `urlopen` for legitimate DOI/URL verification

### 3. File Operations
**Checked for:** `base64`, `pickle`, `yaml.load`, `shutil.copy`, `os.remove`, `rm -rf`

**Result:** ✅ No dangerous file operations found

### 4. External Dependencies
**Checked:** `requirements.txt`

**Result:** ✅ No external dependencies required for basic usage

---

## What This Skill Does

1. **Research Pipeline:** Provides a structured 8-phase research methodology
2. **Citation Tracking:** Manages sources and citations with JSONL persistence
3. **Report Validation:** Checks reports for completeness and quality
4. **Citation Verification:** Verifies DOIs resolve and URLs are accessible
5. **HTML/PDF Output:** Converts reports to professional formats

---

## Known Limitations (Not Security Issues)

1. **search-cli Optional:** For full functionality, requires optional `search-cli` installation
2. **MCP Tools Required:** For local model use, requires SearXNG MCP tools (`mcp__searxng__searxng_web_search`, `mcp__searxng__web_url_read`)
3. **PDF Generation:** Requires WeasyPrint for PDF output (optional)

---

## Recommendation

**SAFE TO USE** - This is a legitimate research productivity tool. Updated to use SearXNG MCP tools (`mcp__searxng__searxng_web_search`, `mcp__searxng__web_url_read`) for local model compatibility.
