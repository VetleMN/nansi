# The Nansi Keyboard Layout

![Norwerty Keyboard Layout](assets/images/norwerty.svg)

This ia fork of [Norwerty](https://github.com/tobiasvl/norwerty) and it has been modified to be similar to [Nansi](https://github.com/oeywil/Nansi), but for Linux.  


* [Norwerty for Linux](#norwerty-for-linux)

<!--The design goal for the Norwerty layout is to retain as much as possible of the standard US layout (also known as the ANSI keyboard layout), while adding the keys <kbd>Æ</kbd>, <kbd>Ø</kbd>, and <kbd>Å</kbd> from the standard Norwegian layout. This alternative software layout is especially useful if you are working on a US keyboard and want to write in Norwegian. Arguably, Norwerty is a better choice than the standard Norwegian layout even if you are working on a Norwegian keyboard, as it incorporates more of the superior key arrangement of the US layout. With the standard Norwegian layout, many frequently used symbols are surprisingly inconvenient to type, such as <kbd>@</kbd> in email addresses, <kbd>/</kbd> in web addresses, and <kbd>$</kbd> in programming. These conventions were set by people who used the US layout where these symbols can be typed conveniently. The Norwerty layout makes it possible to enjoy this convenience while typing in Norwegian.

The idea is to retain most of the US layout, but to have the keys <kbd>Æ</kbd>, <kbd>Ø</kbd>, and <kbd>Å</kbd> in their same positions as in the standard Norwegian layout, replacing the <kbd>;</kbd>, <kbd>'</kbd>, and <kbd>[</kbd> keys in the US layout. The <kbd>]</kbd> key is replaced by a dead key for acute and grave accents. The replaced keys from the US layout are reached by pressing <kbd>AltGr</kbd> and the original key. This basic layout has been altered somewhat in order to suit Mac, Linux, and Windows environments. -->


## Nansi for Linux



### Installation instructions

1. Add the contents of [`no.txt`](https://github.com/VetleMN/nansi/blob/master/no.txt) to the end of the file `/usr/share/X11/xkb/symbols/no`

2. Look up the following section in the file `/usr/share/X11/xkb/rules/evdev.xml`:

```
    <layout>
      <configItem>
        <name>no</name>

        <shortDescription>no</shortDescription>
        <description>Norwegian</description>
        <languageList>
          <iso639Id>nor</iso639Id>
          <iso639Id>nob</iso639Id>
          <iso639Id>nno</iso639Id>
        </languageList>
      </configItem>
      <variantList>
```

3. Add the following variant block after the line `<variantList>`:

```
        <variant>
          <configItem>
            <name>Nansi</name>
            <description>Nansi</description>
          </configItem>
        </variant>
```

4. Finally, after the line `! variant` in the file `/usr/share/X11/xkb/rules/evdev.lst` add the following line:
```
  nansi          no: Nansi
```

Now Nansi should show up as one of the alternative keyboard layouts for Nansi.
