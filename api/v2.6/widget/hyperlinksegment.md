---
layout: page
tags: [api]
title: Fyne API "widget.HyperlinkSegment"
package: fyne.io/fyne/v2/widget
---

# widget.HyperlinkSegment
---
```go
import "fyne.io/fyne/v2/widget"
```

## Usage

#### type HyperlinkSegment

```go
type HyperlinkSegment struct {
	Alignment fyne.TextAlign
	Text      string
	URL       *url.URL

	// OnTapped overrides the default `fyne.OpenURL` call when the link is tapped
	//
	// Since: 2.4
	OnTapped func() `json:"-"`
}
```

HyperlinkSegment represents a hyperlink within a rich text widget.


<div class="since">Since: <code>
2.1</code></div>

#### func (*HyperlinkSegment) Inline

```go
func (h *HyperlinkSegment) Inline() bool
```
Inline returns true as hyperlinks are inside other elements.

#### func (*HyperlinkSegment) Select

```go
func (h *HyperlinkSegment) Select(begin, end fyne.Position)
```
Select tells the segment that the user is selecting the content between the two positions.

#### func (*HyperlinkSegment) SelectedText

```go
func (h *HyperlinkSegment) SelectedText() string
```
SelectedText should return the text representation of any content currently selected through the Select call.

#### func (*HyperlinkSegment) Textual

```go
func (h *HyperlinkSegment) Textual() string
```
Textual returns the content of this segment rendered to plain text.

#### func (*HyperlinkSegment) Unselect

```go
func (h *HyperlinkSegment) Unselect()
```
Unselect tells the segment that the user is has cancelled the previous selection.

#### func (*HyperlinkSegment) Update

```go
func (h *HyperlinkSegment) Update(o fyne.CanvasObject)
```
Update applies the current state of this hyperlink segment to an existing visual.

#### func (*HyperlinkSegment) Visual

```go
func (h *HyperlinkSegment) Visual() fyne.CanvasObject
```
Visual returns a new instance of a hyperlink widget required to render this segment.
