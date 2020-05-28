# Wikimedia Research API Interface Template
This template provides a consistent style and basic building blocks for setting up an interface for experimental APIs built by the WMF Research team -- e.g., as hosted on Toolforge or other Cloud VPS services. The HTML and assets should provide the starting template for any new projects.

## Sections
Template is built on three main sections: `#tool_header`, `#main_content` and `#tool_footer`.

- `#tool_header` contains the Tool's title, meta data and main description.
- `#main_content` is where the actual tool should be placed.
- `#tool_footer` is for acknowledgement links such as the author's profile, related tools, and links of interest.

## General considerations
### Global Classes
All elements can be modified by the use of certain global __HTML classes__.

#### Text alignment
Assigning classes `text--left`, `text--center` or `text--right` aligns text (and inline elements) accordingly.
#### Padding
All elements can obtain padding from classes `padded--top`, `padded--right`, `padded--bottom` and `padded--left` accordingly, or `padded` adds padding on all four sides.

### Text
At any point, to use block of text, whether it's lists, paragraphs, etc, you should add a `text` class to the container.
```html
<div class="text">
	<ul>
		<li></li>
	</ul>
	<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit…</p>
	<ol>
		<li></li>
	</ol>
</div>
```

### Columns
A columns layout can be applied and each column filled with elements of your choice.

To build a columns block, syntax is as follows:
```html
<div class="cols cols4">
	<div class="col col1"></div><!-- column with width 1/4 -->
	<div class="col col2"></div><!-- column with width 2/4 -->
	<div class="col col1"></div><!-- column with width 1/4 -->
</div><!-- columns container with 4 inner columns -->
```
Columns container should have the `cols` class (plural) accompanied by `cols4` for 4 inner columns, or lower numbers for fewer columns.

Similarly, inner column containers should have the `col` class (singular) accompanied by `col1` for _1 of X_ columns (_X_ being inherited from the container) or higher numbers for more columns within the container.

## Elements

### Headings
Secondary headings (_H2_ through _H4_) have a padding at the bottom with a 300px-wide bottom border. This can be deactivated by using the `simple` class on each heading.

### Note
An element with a `note` class (as seen in the Header in this template) makes the block use a smaller font size, and adds a border to the left of the element.

### Description
The description within the `header` has a `padded--left` class by default with adds empty space to the left of the element. Removing this makes the text the full width of the container.

### Separator
A special element can be added to force a thin horizontal line to break content. It's comprised of an empty element with a `separator` class:
```html
<div class="separator"></div>
```

### Cards
Cards are intended as part of the _columns_ layout mentioned previously.

A standard card looks as follows:
```html
<section class="cards">
	<div class="cols cols4">
		<div class="col col1">
			<article class="card has--border"><a href="#">
				<div class="img">
					<figure><img src="…" alt="" /></figure>
				</div><!-- .img -->
				<div class="texts">
					<h3>Name</h3>
					<div class="description">
						<p></p>
					</div>
					<div class="more">More &raquo;</div>
				</div><!-- .texts -->
			</a></article><!-- .card -->
		</div><!-- .col -->
	</div><!-- .cols -->
</section><!-- .cards -->```
```

Within the `cards` containing block, you should build the `cols` holder and within, each `col` creates a card.
Each `col` should contain each `card`, which in itself has 2 elements: an optional _image_ and _texts_.

__Image__ automatically fills up the containing box which is _100%_ wide (the holding column's width) and _180px_ tall, but you should use images relatively similar in proportion and with its main content focused at the center of the image (due to responsive layouts adaptation).

__Texts__ holds the name of the card in an _h3_ element, the _description_ and a _more_ button. All optional.

Additionally, cards can have an optional visual style, activated by adding a `has--border` class to the `card` element. This class adds a border, rounded corners and a visual hover effect on the optional _more_ button.

## Additional Information
This template is provided under MIT License. Initial development done with support from [Diego Quintana](https://diegoquintana.com/).
