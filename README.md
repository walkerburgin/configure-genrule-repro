# `configure-genrule-repro`

See [`gazelle/js/tests/simple_import_generated`](https://github.com/aspect-build/aspect-cli/tree/848653ce3783885bcf30b2c8726bbe3ca90c2caa/gazelle/js/tests/simple_import_generated)

## Repro
- Run `bazel configure`
- Run `bazel build //...` and observe a build failure:
  ```
  ➜  configure-genrule-repro (develop) bazel build //...
  ERROR: /Users/walkerburgin/Repositories/walkerburgin/configure-genrule-repro/pkgs/foo-lib/BUILD.bazel:19:11: in deps attribute of ts_project rule //pkgs/foo-lib:typescript: generated file '//pkgs/foo-lib:r1.ts' is misplaced here (expected no files). Since this rule was created by the macro 'ts_project', the error might have been caused by the macro implementation
  ERROR: /Users/walkerburgin/Repositories/walkerburgin/configure-genrule-repro/pkgs/foo-lib/BUILD.bazel:19:11: in deps attribute of ts_project rule //pkgs/foo-lib:typescript: generated file '//pkgs/foo-lib:r2.d.ts' is misplaced here (expected no files). Since this rule was created by the macro 'ts_project', the error might have been caused by the macro implementation
  ERROR: /Users/walkerburgin/Repositories/walkerburgin/configure-genrule-repro/pkgs/foo-lib/BUILD.bazel:19:11: Analysis of target '//pkgs/foo-lib:typescript' failed
  ```