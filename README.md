# 30293 

Reproduction repository for [Renovate discussion 30293](https://github.com/renovatebot/renovate/discussions/30293)

## Current behavior



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

2. `npx renovate jonathanmartens/renovate-discussion-30293` should not complain about preset

## Link to the Renovate issue or Discussion

https://github.com/renovatebot/renovate/discussions/30293
