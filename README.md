# tm-u220-skill

A Claude skill for programming the Epson TM-U220 9-pin impact receipt printer over ESC/POS:
text styles, red printing, images and charts that come out right on a dot matrix head.

> [!WARNING]
> Written by AI from Epson's documentation and test prints on one TM-U220 (firmware 3.13,
> Chinese GB18030 model). `reference.md` lists what was checked on paper and what wasn't tried.

## Contents

- [`skills/printing-on-epson-tm-u220/SKILL.md`](skills/printing-on-epson-tm-u220/SKILL.md): what works on this printer and what doesn't
- [`reference.md`](skills/printing-on-epson-tm-u220/reference.md): command table, measurements, sources
- [`scripts/tmu220.py`](skills/printing-on-epson-tm-u220/scripts/tmu220.py): Python 3 helpers, standard library only, with a short demo
- [`scripts/full_demo.py`](skills/printing-on-epson-tm-u220/scripts/full_demo.py): prints every feature: text styles, a receipt, shading, charts

## Install

In Claude Code, as a plugin:

```
/plugin install tm-u220 --marketplace StevenGuo42/tm-u220-skill
```

On Claude Code older than 2.1.275, add the marketplace first:

```
/plugin marketplace add StevenGuo42/tm-u220-skill
/plugin install tm-u220@tm-u220-skill
```

Or copy the skill folder into your personal skills:

```sh
cp -r skills/printing-on-epson-tm-u220 ~/.claude/skills/
```

## Try it

```sh
python skills/printing-on-epson-tm-u220/scripts/tmu220.py selftest
python skills/printing-on-epson-tm-u220/scripts/tmu220.py id <printer-ip>
python skills/printing-on-epson-tm-u220/scripts/tmu220.py demo <printer-ip>
python skills/printing-on-epson-tm-u220/scripts/full_demo.py <printer-ip>
```

## Data and network

The scripts send print jobs only to the printer address you give them, over raw TCP port 9100
on your own network. Nothing goes to any other service, and nothing is stored or collected.

## License

MIT, see [LICENSE](LICENSE).
