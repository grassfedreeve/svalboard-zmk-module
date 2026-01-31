# Svalboard ZMK Module

This is the ZMK module for the Svalboard

## Usage

Add these lines to `config/west.yml` in your `zmk-config` repository:

```yaml
manifest:
  remotes:
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: grassfedreeve                         # <---
      url-base: https://github.com/grassfedreeve  # <---
    - name: george-norton			  # <---
      url-base: https://github.com/george-norton  # <---
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: svalboard-zmk-module
      remote: grassfedreeve
      revision: trackballs
    - name: zmk-driver-pmw3360
      remote: george-norton
      revision: main
  self:
    path: config
```

Then add the `svalboard` board to your `build.yaml`:

```yaml
---
include:
  - board: svalboard_left
  - board: svalboard_right

```

For more information on ZMK Modules and building locally, see [the ZMK docs page on modules.](https://zmk.dev/docs/features/modules)

