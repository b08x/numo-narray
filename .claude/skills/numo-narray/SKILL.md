```markdown
# numo-narray Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you the core development patterns, coding conventions, and maintenance workflows for contributing to the [numo-narray](https://github.com/ruby-numo/numo-narray) Ruby library. numo-narray is a high-performance numerical array library for Ruby, featuring a C extension for speed. This guide covers how to work with its codebase, including C and Ruby code, testing, CI updates, and common maintenance tasks.

## Coding Conventions

**File Naming**
- Uses `camelCase` for file names.
  - Example: `myFile.rb`, `myTestFile.rb`

**Import Style**
- Uses relative imports in Ruby.
  - Example:
    ```ruby
    require_relative '../lib/numo/narray'
    ```

**Export Style**
- Uses named exports (explicitly exporting classes, modules, or methods).
  - Example:
    ```ruby
    module Numo
      class NArray
        # ...
      end
    end
    ```

**Commit Messages**
- Freeform, no strict prefix.
- Average length: ~39 characters.

## Workflows

### CI Workflow Update
**Trigger:** When updating, fixing, or enhancing the GitHub Actions CI workflow (e.g., Ruby versions, Fedora builds, deprecations).
**Command:** `/update-ci`

1. Edit `.github/workflows/build.yml` to add or update jobs, runners, or steps.
2. Optionally update `numo-narray.gemspec` if dependencies or Ruby version changes are involved.
3. Commit and push changes.
4. Merge the pull request if applicable.

**Files Involved:**
- `.github/workflows/build.yml`
- `numo-narray.gemspec`

---

### Feature or Bugfix with Test
**Trigger:** When adding a new feature or fixing a bug in the core library and ensuring it is tested.
**Command:** `/feature-with-test`

1. Edit or add implementation in `ext/numo/narray/numo/types/*.h` or related C files.
2. Update or add tests in `test/*.rb`.
3. Commit and push changes.
4. Merge the pull request if applicable.

**Files Involved:**
- `ext/numo/narray/numo/types/*.h`
- `test/*.rb`

**Example:**
```c
// ext/numo/narray/numo/types/int32.h
static VALUE
int32_add(VALUE self, VALUE other) {
  // implementation
}
```
```ruby
# test/test_int32.rb
require_relative '../lib/numo/narray'
# ... test cases for int32_add
```

---

### Bulk Typo or Doc Fix
**Trigger:** When cleaning up spelling, comments, or documentation inconsistencies.
**Command:** `/fix-typos`

1. Edit source files, documentation, and comments to fix typos or clarify language.
2. Commit and push changes.
3. Merge the pull request if applicable.

**Files Involved:**
- `ext/numo/narray/**/*.c`
- `ext/numo/narray/**/*.h`
- `ext/numo/narray/gen/**/*.c`
- `ext/numo/narray/gen/**/*.rb`
- `lib/numo/narray/*.rb`
- `doc/*.md`
- `ToDo.md`

---

### Test Fix or Enhancement
**Trigger:** When fixing, updating, or improving test assertions or coverage.
**Command:** `/fix-test`

1. Edit `test/*.rb` files to fix or enhance tests.
2. Commit and push changes.
3. Merge the pull request if applicable.

**Files Involved:**
- `test/*.rb`

**Example:**
```ruby
# test/test_narray.rb
def test_addition
  assert_equal expected, Numo::NArray[1,2,3] + 1
end
```

---

### C Extension Bulk Refactor or Fix
**Trigger:** When modernizing code, fixing compiler warnings, or refactoring C source.
**Command:** `/refactor-c-extension`

1. Edit multiple files in `ext/numo/narray/` and subdirectories.
2. Commit and push changes.
3. Merge the pull request if applicable.

**Files Involved:**
- `ext/numo/narray/**/*.c`
- `ext/numo/narray/**/*.h`

**Example:**
```c
// Before: old pointer usage
int *ptr = (int*)malloc(sizeof(int)*n);

// After: safer allocation
int *ptr = ALLOC_N(int, n);
```

## Testing Patterns

- Test files are Ruby scripts matching `test/*.rb`.
- Testing framework is unknown, but tests are written as Ruby assertions.
- Example test file:
  ```ruby
  # test/test_narray.rb
  require_relative '../lib/numo/narray'

  def test_sum
    a = Numo::NArray[1,2,3]
    assert_equal 6, a.sum
  end
  ```

## Commands

| Command                | Purpose                                                      |
|------------------------|--------------------------------------------------------------|
| /update-ci             | Update or fix GitHub Actions CI workflow                     |
| /feature-with-test     | Add a feature or bugfix with corresponding tests             |
| /fix-typos             | Fix typos or documentation issues across the codebase        |
| /fix-test              | Fix, update, or enhance tests                                |
| /refactor-c-extension  | Refactor or modernize C extension source files               |
```
