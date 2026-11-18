# Software Versioning & Quality Control Process at IISD-ELA
> The contents in this section were migrated from the `versioning-instructions.md` file from the [IISD-ELA/github-documentation-files](https://github.com/IISD-ELA/github-documentation-files/tree/main/docs) repository.

*Created on:* June 16, 2026
*Last Updated:* July 7, 2026  
*Branched from the Prairie Watershed Analytics project on Sept. 1, 2026*

*Author(s):* Thomas Saleh

---

## 1. Reference Architecture

The following diagrams document the current state of the codebase and should be updated whenever structural changes are made.

| Name & Link | Description |
| --- | --- |
| [Data Flow Diagram](https://iisdnet.sharepoint.com/:u:/s/IISDWaterPolicy/IQCCsW3BZjkDR5B1qyORnz9VAXVBwoWsMforHCjdE5iCvWg?email=shood%40iisd-ela.org&e=tdue2W) | End-to-end flow of data through the pipeline |
| Module Architecture (p.2) | Conventions for Python package/module structure |

> ⚠️ If a proposed change materially alters either diagram, or if the existing diagrams do not completely and accurately represent the affected code (new or existing), updated versions must be included with the pull request.

---

## 2. Change Classification & Versioning

All changes must be classified before development begins. Classification determines the version increment and the level of testing required before merging.

We follow Semantic Versioning: `MAJOR.MINOR.PATCH`

### 2.1 Change Types

| Change Type | Description | Version Increment |
| --- | --- | --- |
| Bug Fix | Corrects incorrect behavior without changing interfaces or features | x.x.+1 (Patch) |
| Improvement | Optimisation, refactor, or non-breaking enhancement to existing functionality | x.x.+1 (Patch) |
| New Feature | Adds new capability; existing functionality unchanged | x.+1.0 (Minor) |
| Interface Change | Modifies inputs, outputs, or APIs of existing modules | x.+1.0 (Minor) |
| Breaking Change | Alters core architecture, data contracts, module interfacing, or removes functionality | +1.0.0 (Major) |

### 2.2 Testing Requirements by Version Level

| Version Level | Unit Tests | Integration Tests | Regression Tests | Intermediate Output Check | Architecture Diagram Update |
| --- | --- | --- | --- | --- | --- |
| Patch x.x.+1 | Affected module only | Not required | Lightweight (final outputs) | Not required | Not required |
| Minor x.+1.0 | All affected modules | Required at module boundaries | Full regression suite | Recommended | If structure changed |
| Major +1.0.0 | Full suite | Full suite | Full regression suite + tolerance checks | Required at all steps | Required |

### 2.3 Before You Write Any Code

1. Classify the change using Sections 2.1 & 2.2 above and note the version increment
2. Create a new branch from main (or your default branch):
   - `git checkout -b feature/short-description` — for new features
   - `git checkout -b fix/short-description` — for bug fixes
3. Write a brief change spec (1–5 sentences, to be included with the pull request) describing:
   - What the change does
   - Why it's needed
   - Which modules are affected

---

## 3. Testing Protocol

Tests should be written before introducing any new functions or code to any of the source codebase. Tests and function definitions can be drafted jointly using Jupyter notebooks. See sections 2.2, 2.3, and 4.1 for reference.

If issues in error handling are identified during the testing process, document them and include them with the pull request (along with any supporting context).

### 3.1 Unit Tests

- Write or update unit tests in `[tests/ directory]` for every new or modified function
- Each test should cover:
  - [ ] Normal expected inputs
  - [ ] Edge cases (empty inputs, boundary values, unexpected types) (minor & major updates)
  - [ ] Expected failure modes (confirm errors raise correctly) (minor & major updates)
- Run with:

```
pytest tests/… -v
```

### 3.2 Integration Tests

- Test interactions between modules, especially at boundaries introduced by the refactor
- Confirm data passed between modules is in the expected format and shape
- If no integration test exists, and integration is required, the integration test must be built.

### 3.3 Regression Tests

- Run the full pipeline against the reference input dataset (path to reference data TBD)
- Compare final outputs against the reference output baseline (path to reference data TBD)
- For numerical outputs, apply tolerance checks:

```python
import numpy as np
assert np.allclose(new_output, reference_output, atol=1e-6), "Regression check failed"
```

### 3.4 Intermediate Output Checks (Major changes only)

- Log and compare intermediate outputs at each pipeline step against the old codebase
- Document any intentional deviations and justify them in the PR

### 3.5 Coverage Check

```
pytest --cov=[modified_package] --cov-report=term-missing
```

Aim to maintain or improve coverage with each change. Do not merge if coverage drops significantly without justification.

---

## 4. Development Workflow

### 4.1 Prototyping in Jupyter Notebooks

Jupyter notebooks are used for development and experimentation only — they are not part of the production codebase.

Steps (recommended, but optional):

1. Create a new notebook in `[notebooks/ directory or agreed location]`
2. Name it descriptively: `YYMMDD_watershed_descriptor.ipynb`
3. At the top of the notebook, include:
   - Purpose of the notebook
   - Input data used for testing
   - Expected outputs or success criteria
4. Develop and iterate your logic in notebook cells
5. If issues in error handling are identified during this process, document them and include them with the pull request (along with any supporting context)
6. Log intermediate outputs using summary statistics at key steps (consider using `logging`):

```python
import logging
logger = logging.getLogger(__name__)

def new_step(data):
    result = process(data)
    logger.debug("new_step output: %s", result)
    return result
```

7. Once satisfied, identify the clean, reusable logic to extract into the module

---

### 4.2 Inserting Code into Python Modules

Once notebook logic is validated:

1. Identify the target module(s) — refer to the diagrams in Section 1
2. Extract clean functions from the notebook — remove exploratory code, ensure:
   - Clear function names and docstrings
   - Type hints on inputs and outputs where practical
   - Meaningful error handling (raise informative exceptions, don't fail silently)
3. Insert into the appropriate module, respecting the existing structure:

```python
def new_function(input: type) -> type:
    """
    Brief description of what this function does.

    Args:
        input: description

    Returns:
        description

    Raises:
        ValueError: description of when this is raised
    """
    ...
```

4. Update `__init__.py` if the new function needs to be exposed at the package level
5. Run tests from part 3.
6. Update the architecture diagram if module structure has changed

---

## 5. Pull Request Checklist

All pull requests must include the following information:

**Change Summary**

- [ ] Change type (Bug Fix / Improvement / New Feature / Interface Change / Breaking Change)
- [ ] Version increment (Patch / Minor / Major) and new version number
- [ ] Brief description of what changed and why
- [ ] Modules affected

**Testing Evidence**

- [ ] Unit tests written/updated and passing
- [ ] Integration tests run (if Minor or Major)
- [ ] Regression test results included (pass/fail + any notable deltas)
- [ ] Intermediate output checks completed (if Major)
- [ ] Coverage report attached or summarised (skip for patches, run `python -m pytest --cov <path>`)

**Documentation**

- [ ] Docstrings added/updated for all changed functions
- [ ] Architecture or data flow diagrams updated (if applicable)
- [ ] This QC document updated (if process has changed)
- [ ] Error handling issues flagged for review where applicable
- [ ] Versioning notes added to log (below, minor & major changes only)

---

## 6. Versioning Log

**PWA main package**

| Version | Date | Change Type | Description | Author |
| --- | --- | --- | --- | --- |
| 1.0.0 | June 16, 2026 | Initial Release | Post-refactor baseline | Amanbir Singh |

**PWA raven package**

| Version | Date | Change Type | Description | Author |
| --- | --- | --- | --- | --- |
| 0.2.0 | July 7, 2026 | New Feature | Frequency Analysis module | Thomas Saleh (+ Claude) |
| 0.1.0 | June 16, 2026 | Initial Release | Post-refactor baseline | Amanbir Singh |

