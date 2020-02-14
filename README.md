## Cascade and Specificity
Process of combining different stylesheets and resolving conflicts between different CSS rules and declarations, when more than one rule applies to a certaint element.

### Author Declarations
CSS that we the developers write, declarations that we put in stylesheets are called Author Declarations

### User Declarations
CSS coming from the user, ie: When the user changes the font size in the browser, then this is User CSS.

### Browser Declarations (User Agent)
Default style in elements, i.e: anchor tag (blue and underline)

### IMPORTANCE > SPECIFICITY > SOURCE ORDER

### IMPORTANTE
* 1. User !important declarations.
* 2. Author !important declarations.
* 3. Author declarations.
* 4. User declarations.
* 5. Default browser declarations.

Same importante? ->

### SPECIFICITY
* 1. Inline styles.
* 2. IDs.
* 3. Classes, pseudo-classes, attribute.
* 4. Elements, pseudo-elements.

Same specificity? ->

### SOURCE ORDER
The last declaration in the code will override all other declarations and will be applied.

Notes:
* Only use !important as a last resource. It's better to use correct specifities - more maintainable code!.
* The universal selector * has no specificity value (0,0,0,0).
* Rely more on specificity than on the order of selectors.
* But, rely on order when using 3rd-party stylesheets -- always put your author stylesheet last.

## Value Processing
CSS Engine converts relative units to pixels
* REM -> Relative , i.e: 1.5 rem means 1.5 times the default size
|   | Source  | Example(x) | How to convert to pixels | Results in pixel |
| - | --------| -----------| ------------------------ | ---------------- |
| % (fonts)   | 16px | 150% | x% * parent computed font size | 24px |
| % (lengths) | 1000px | 10% | x% -> parent computed font size | 100px |
| em (fonts)  | 24px | 3em | x * parent computed font size | (24px*3) = 72px |
| em (length) | 24px | 2em | x * current element computed font size | (24px*2) = 48px |
| rem | 16px  | 10rem | x * root computed font size | (16px*10) = 24px |
| vh  |       | 90vh  | x * 1% of viewport height   | 90% of the current viewport height |
| vw  | ----  | 80vw  | x * 1% of viewport width   | 90% of the current viewport width |

Notes:
* em - rem are font-based.
* vh (viewport-height) - vw(viewport-width)  are viewport-based.

Why should we actually size stuff with ems and rems if they are based on font-size?
We can build more robust responsive layouts because just by changing font sizes, we will automatically change length since it depend on a font size. That gives us a lot of flexibility.

Notes:
* Each property has an initial value, used if nothing is declared ( and if there is no inheritance).
* Browsers specify a root font-size for each page (usually 16px - user agent definition).
* Percentages and relative values are always converted to pixels.
* Percentages are measured relative to their parent's font-size, if used to specify font-size.
* Percentages are measured relative to their parent's width, if used to specify lengths.
* em are measured relative to their parent font-size, if used to specify font-size.
* em are measured relative to the current font-size, if used to specify lengths.
* rem are always measured relative to the document's root font-size.
* vh and vw are simply percentage measurements of the viewports height and width.

## Inheritance
* Inheritance passes the values for some specific properties from parents to children - more manintainable code.
* Properties related to text are inherited. font-family, font-size, color, etc.
* Inheritance of a property only works if no one declares a value for that property.
* The inherit keyword forces inheritance on a certain property.
* The initial keyword resets a property to its initial value.