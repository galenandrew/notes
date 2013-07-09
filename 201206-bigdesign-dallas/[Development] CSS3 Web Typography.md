# CSS3 Web Typography Changes Everything
@date: 2012/06/01
@speaker: Thomas Phinney, @ThomasPhinney (Designed Hypatia Sans!!)

## Agenda
- Web Fonts Quick Overview
- OpenType Demo

## Real Fonts
- Standards Based
- Replaces various hacks & stopgaps
- From web server
- Downloaded to viewers browsers
- Same text rendering as other fonts
- Regular font files (+ wrapper)
- - TTF/OTF
- - ETF/WOFF is a wrapper around regular font

## Challenges
- Most fonts not licensed for web
- Many formats required
- - EOT, TTF, OTF, (SVG), WOFF
- Browsers constantly changing

## Integration / Implementation
- Self-hosted
- Hosted web font service
- Recommends a level of abstraction b/w font and self-named font family in CSS. Promotes ease of use by utilitarian naming conventions.

## OpenType Features in CSS
- CSS attributes
`font-feature-settings` (Ligatures/Kerning)
`text-rendering`

## Demo (OpenType Features)
* Standard Ligatures
'ff/fi/Th'
* All Caps (typed vs formatted)
shifts elements up to correct height (dashes, parens, punctiation)
* Small Caps (faux vs real)
when scaling cap font down it scales stroke weight VS designed w/ scaled with same weight
* Basic Figure Styles (Numbers - lining)
- Tabular: Same width
- Proportional: varied width
- Proportional Oldstyle: below x-height
* Ordinals & Fractions (faux vs real)
- same as small caps…scaled
* Stylistic Sets
Many levels of Swashes

## Resources
- http://mzl.la/ff4-ot
- http://w3.org/TR/css3-fonts
- http://blog.webink.com
- http://thomasphinney.com
- http://tktype.com/chartwell.php