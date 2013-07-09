# Surviving CSS by Thriving with SASS
@date: 2012/06/01
@speaker: Ken Tabor, @KenTabor
@presentation: bit.ly/kenbigd12

## About Ken
coder of mobile web apps
works @ Saber (Southlake) - travel related
presentation built w/ deck.js
IDE: PHPStorm by Jetbrain

## Problems w/ CSS
- Designers think it looks too much like programming
- Developers think it lacks structure, c/p spaghetti-code disasters
- Not easily shareable

## SASS
- Meta language extending CSS by wrapping it up into organization
- `.scss` -> `.css`
### The Best Parts
**Mixins**
Encapsulate commonly used CSS patterns into little resuable snippets

**Parameters**
Pass variables into mixins and functions

**Variables**
Assign named resource a value

**Functions**
Analogy to mixins, but has a little differences

**Hierarchical Nesting**
Selectors inside Selectors

**Color Math**
Modify colors 

**File Fragments**
'Partials'

**Modern Comments**
`// …` instead of `/* … */`

**@Import**
- CSS @imports establish additional HTTP requests
- SASS @imports are pre-processor
- underscores in filenames in SASS are partials and don't get compiled into CSS

**Output File Formats**
- Ability to compress within compiler `--style-nested` vs `--style-compressed`

## Resources
- SASS is built in Ruby and installed via gems
**Apps / GUIs**
- Scout @github.com/mhs/scout-app
- Compass (includes Compass Framework)
- CodeKit (for developers, compiles multi-metalanguages)