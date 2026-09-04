# calebBoard — ZMK Corne Config

A 3-layer ZMK keymap for the [Corne (CRKBD)](https://github.com/foostan/crkbd) powered by nice!nano v2.

## Layers

### Layer 0 — Default (QWERTY + Home-Row Mods)

```
┌─────┬─────┬─────┬─────┬─────┐           ┌─────┬─────┬─────┬─────┬─────┐
│ ESC │  W  │  E  │  R  │  T  │           │  Y  │  U  │  I  │  O  │  P  │
│  Q  │     │     │     │     │           │     │     │     │     │     │
├─────┼─────┼─────┼─────┼─────┤           ├─────┼─────┼─────┼─────┼─────┤
│  A  │  S  │  D  │  F  │  G  │           │  H  │  J  │  K  │  L  │ ENT │
├─────┼─────┼─────┼─────┼─────┤           ├─────┼─────┼─────┼─────┼─────┤
│  Z  │  X  │  C  │  V  │  B  │           │  N  │  M  │  ,  │  .  │ TAB │
└─────┴─────┴─────┴─────┴─────┘           └─────┴─────┴─────┴─────┴─────┘
          ┌─────┬─────┬─────┐             ┌─────┬─────┬─────┐
          │WIN  │LWR  │SPC  │             │SPC  │RSE  │ ALT │
          │     │ DEL │CTRL │             │SHIFT│BSPC │     │
          └─────┴─────┴─────┘             └─────┴─────┴─────┘
```

- **Q** taps `ESC` when held — `&mt ESC Q`
- **Left thumb cluster:** `LGUI` | `LWR(DEL)` | `CTRL(SPC)`
- **Right thumb cluster:** `SHIFT(SPC)` | `RSE(BSPC)` | `LALT`

### Layer 1 — Number & Navigation (hold LWR)

```
┌─────┬─────┬─────┬─────┬─────┐           ┌──────┬──────┬──────┬──────┬─────┐
│  1  │  2  │  3  │  4  │  5  │           │ BT1  │ BT2  │ BT3  │ BT4  │ F12 │
├─────┼─────┼─────┼─────┼─────┤           ├──────┼──────┼──────┼──────┼─────┤
│  6  │  7  │  8  │  9  │  0  │           │ LEFT │ DOWN │  UP  │ RIGHT│ F11 │
├─────┼─────┼─────┼─────┼─────┤           ├──────┼──────┼──────┼──────┼─────┤
│ F1  │ F2  │ F3  │ F4  │ F5  │           │  F6  │  F7  │  F8  │  F9  │ F10 │
└─────┴─────┴─────┴─────┴─────┘           └──────┴──────┴──────┴──────┴─────┘
          ┌─────┬─────┬─────┐             ┌─────┬─────┬─────┐
          │ GUI │     │ SPC │             │ ENT │     │ ALT │
          └─────┴─────┴─────┘             └─────┴─────┴─────┘
```

- Numbers 0–9 on left half
- **Right half:** Bluetooth selector (BT_SEL 0–3) + arrow cluster
- F1–F12 along bottom row

### Layer 2 — Code / Symbols (hold RSE)

```
┌─────┬─────┬─────┬─────┬─────┐           ┌─────┬─────┬─────┬─────┬─────┐
│  !  │  @  │  #  │  %  │  |  │           │  &  │  ^  │  *  │  ?  │  `  │
├─────┼─────┼─────┼─────┼─────┤           ├─────┼─────┼─────┼─────┼─────┤
│  $  │  <  │  (  │  [  │  {  │           │  }  │  ]  │  )  │  >  │  ~  │
├─────┼─────┼─────┼─────┼─────┤           ├─────┼─────┼─────┼─────┼─────┤
│ BT  │  \  │  .  │  -  │  =  │           │  _  │  +  │  ;  │  /  │  ,  │
│ CLR │     │     │     │     │           │     │     │     │     │     │
└─────┴─────┴─────┴─────┴─────┘           └─────┴─────┴─────┴─────┴─────┘
          ┌─────┬─────┬─────┐             ┌─────┬─────┬─────┐
          │ GUI │     │ SPC │             │ ENT │     │ ALT │
          └─────┴─────┴─────┘             └─────┴─────┴─────┘
```

- All shifted symbols (`!@#$%^&*()`, brackets, etc.)
- `BT_CLR` (Bluetooth clear) on bottom-left
- Underscore `_`, `+`, `;`, `/`, `,` on right bottom row

## Building

Trigger a build via [GitHub Actions](.github/workflows/build.yml) — pushes to `main` or manual dispatch build the firmware for both halves.

```bash
# Left half
west build -b nice_nano_v2 -d build/left  -- -DSHIELD=corne_left
# Right half
west build -b nice_nano_v2 -d build/right -- -DSHIELD=corne_right
```

## Hardware

| Component | Model |
|-----------|-------|
| Board     | nice!nano v2 |
| Shield    | Corne (CRKBD) |
| Display   | Not configured |
| RGB       | Not configured |
