# scheme-cycle
Schedule specific color schemes based on time of day

# Why?
It felt easier to transition from a bright and light interface during the day to a darker one at night using cronjobs. 

# Install
Requires the installation of [dynamic-colors](https://github.com/sos4nt/dynamic-colors)

1. Follow the setup instructions found [here](https://github.com/sos4nt/dynamic-colors#setup) (NOTE: It is important that dynamic colors is installed to `~/.dynamic-colors` in order for this script to function properly)
2. Once setup, develop a new color scheme as suggested [here](https://github.com/sos4nt/dynamic-colors#developing-color-schemes)
3. Clone this repository into `~/.scheme-cycle`
```
    $ git clone https://github.com/idealwebsolutions/scheme-cycle ~/.scheme-cycle
```
4. Add the tool to your `PATH` by adding it to a persistent configuration file like `.profile`
```bash
    $ export PATH="$HOME/.scheme-cycle/bin:$PATH"
```
5. Need autocompletion? Try
```bash
    $ source ~/.scheme-cycle/bin/scheme-cycle
```

# Usage
Note: All scheduled "scheme cycles" are installed via crontab

Assuming we have a color scheme called "lightness"...

To schedule a new scheme cycle:
```bash
    $ scheme-cycle schedule Morning 6am lightness
```

What happened? If successful, every Morning at 6am the color scheme "lightness" is recolored to every available terminal.
Note: Hours are specified on a 12 hour schedule (1-12 am or pm)

To clear a scheduled cycle:
```bash
    $ scheme-cycle clear Morning
```

What happened? If successful, the scheduled cycle "Morning" is removed and no longer active.

To test out a new color scheme across every terminal
```bash
    $ scheme-cycle recolor lightness
```

What happened? If successful, every available terminal is recolored using the specified color scheme.

# License
MIT
