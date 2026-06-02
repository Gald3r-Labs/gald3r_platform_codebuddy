# Adding Gald3r to an Existing Project (CodeBuddy (Tencent))

Add gald3r to a project that **already exists**, for use with **CodeBuddy (Tencent)**.

For a brand-new project, see [instructions_new_project.md](./instructions_new_project.md).

---

## Step 1 - Get the `codebuddy/` payload

```bash
git clone --depth 1 https://github.com/wrm3/gald3r_platform_codebuddy.git
```

---

## Step 2 - Copy the contents into your project root

**bash / macOS / Linux:**
```bash
cp -r gald3r_platform_codebuddy/codebuddy/. /path/to/your/existing/project/
```

**Windows PowerShell:**
```powershell
Copy-Item -Recurse -Force .\gald3r_platform_codebuddy\codebuddy\* C:\path\to\your\project\
```

> **Additive, not destructive.** gald3r drops in its config + `.gald3r/` state and does not
> modify your source. Don't overwrite same-named files unless you mean to. Your project keeps
> its own LICENSE and docs.

---

## Step 3 - Open in CodeBuddy (Tencent)

Reload the project in CodeBuddy (Tencent). gald3r auto-loads from its config.

---

## Step 4 - Verify

Type `@g-status`.

---

*Full docs: [README.md](./README.md) | [CHANGELOG.md](./CHANGELOG.md) | [all 34 tools](https://github.com/wrm3/gald3r)*
