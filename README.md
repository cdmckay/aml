# aml

The Atheria Markup Language: a tag-based format for building areas for Atheria, a MUD based on CircleMUD, and a Perl translator that turns it into CircleMUD's world files. Written in May 2000.

Writing CircleMUD zone files by hand meant remembering which number went on which line. AML gives each field a tag instead:

```
<ZONE 12>

<VIRTUAL 04>
<NAME> Floating Slab </NAME>
<DESC>
You appear to be in the middle of a floating slab of smooth,
flat rock. ...
</DESC>
<BIT> NOMOB GODROOM </BIT>
<TYPE> INSIDE </TYPE>
<DIR D>
	<LINK> 1000 </LINK>
	<DESC> You see a statue of some important figure below you. </DESC>
	...
</DIR>
```

`aml slab.rml` then writes the matching `.wld` file. The [design notes](doc/aml-design.txt) plan one AML file type per CircleMUD file type:

| AML | CircleMUD | Holds |
|---|---|---|
| `.rml` | `.wld` | rooms |
| `.mml` | `.mob` | mobs |
| `.oml` | `.obj` | objects |
| `.sml` | `.shp` | shops |
| `.zml` | `.zon` | zones |

Only rooms got done. The [development log](doc/aml.0.x.x.log) lists what came next: a tag checker, a reverse translator, and the other four types. [`examples/rml/slab.rml`](examples/rml/slab.rml) is a sample room file.

## History

The commits follow the versions that survived, tagged `v0.1.0`, `v0.1.1` and `v0.1.2` (15 to 18 May 2000).

The last commit adds [SHADE](shade/SHADE.txt): design notes for a Perl CGI zone builder that would have put a web front end on AML. It never got past the notes and a prototype XML file.

## Licence

MIT (see [LICENSE](LICENSE)).
