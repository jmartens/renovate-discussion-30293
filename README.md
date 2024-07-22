# 30293 

Reproduction repository for [Renovate discussion 30293](https://github.com/renovatebot/renovate/discussions/30293)

## Current behavior

`npx renovate jonathanmartens/renovate-discussion-30293` throws preset error `"validationError": "Preset is invalid JSON (local>jonathanmartens/renovate-config:default.json5)"`
```
>npx renovate jonathanmartens/renovate-discussion-30293
(node:150248) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
 INFO: Repository started (repository=jonathanmartens/renovate-discussion-30293)
       "renovateVersion": "37.439.0"
 INFO: Throwing preset error (repository=jonathanmartens/renovate-discussion-30293)
       "validationError": "Preset is invalid JSON (local>jonathanmartens/renovate-config:default.json5)"
 INFO: Repository has invalid config (repository=jonathanmartens/renovate-discussion-30293)
       "error": {
         "validationError": "Preset is invalid JSON (local>jonathanmartens/renovate-config:default.json5)",
         "message": "config-validation",
         "stack": "Error: config-validation\n    at fetchPreset (C:\\Users\\jonathan.martens\\AppData\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modules\\renovate\\lib\\config\\presets\\index.ts:410:19)\n    at processTicksAndR
ejections (node:internal/process/task_queues:95:5)\n    at Object.resolveConfigPresets (C:\\Users\\jonathan.martens\\AppData\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modules\\renovate\\lib\\config\\presets\\index.ts:331:31)\n
    at mergeRenovateConfig (C:\\Users\\jonathan.martens\\AppData\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modules\\renovate\\lib\\workers\\repository\\init\\merge.ts:226:5)\n    at getRepoConfig (C:\\Users\\jonathan.martens\\
AppData\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modules\\renovate\\lib\\workers\\repository\\init\\config.ts:14:12)\n    at initRepo (C:\\Users\\jonathan.martens\\AppData\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modul
es\\renovate\\lib\\workers\\repository\\init\\index.ts:55:12)\n    at Object.renovateRepository (C:\\Users\\jonathan.martens\\AppData\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modules\\renovate\\lib\\workers\\repository\\index
.ts:62:14)\n    at attributes.repository (C:\\Users\\jonathan.martens\\AppData\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modules\\renovate\\lib\\workers\\global\\index.ts:218:11)\n    at start (C:\\Users\\jonathan.martens\\App
Data\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modules\\renovate\\lib\\workers\\global\\index.ts:203:7)\n    at C:\\Users\\jonathan.martens\\AppData\\Local\\npm-cache\\_npx\\05eeecd92f4e18e0\\node_modules\\renovate\\lib\\renovate.ts:18:22"
       }
 WARN: Issues are disabled - cannot ensureIssue (repository=jonathanmartens/renovate-discussion-30293)
 INFO: Repository finished (repository=jonathanmartens/renovate-discussion-30293)
       "cloned": true,
       "durationMs": 5179
 INFO: Renovate was run at log level "info". Set LOG_LEVEL=debug in environment variables to see extended debug logs.
>


## Expected behavior

Renovate should allow the preset value in extends since it seems to adhere to example in row 3 from [the documentation](https://docs.renovatebot.com/config-presets/#self-hosted-git)

1. `npx --package renovate -- renovate-config-validator renovate.json` should state config is valid:
```
npx --package renovate -- renovate-config-validator config.js
(node:153828) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
 INFO: Validating config.js
 INFO: Config validated successfully
```

2. `npx renovate jonathanmartens/renovate-discussion-30293` should not throw preset error `"validationError": "Preset is invalid JSON (local>jonathanmartens/renovate-config:default.json5)"` and continue its flow.

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/30293
