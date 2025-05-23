---
layout: page
tags: [api]
title: Fyne API "test"
package: fyne.io/fyne/v2/test
---

# test
---
```go
import "fyne.io/fyne/v2/test"
```

Package test provides utility drivers for running UI tests without rendering to a screen.

## Usage

#### func  ApplyTheme

```go
func ApplyTheme(t *testing.T, theme fyne.Theme)
```
ApplyTheme sets the given theme and waits for it to be applied to the current app.

#### func  AssertAllColorNamesDefined

```go
func AssertAllColorNamesDefined(t *testing.T, th fyne.Theme, themeName string)
```
AssertAllColorNamesDefined asserts that all known color names are defined for the given theme.

#### func  AssertCanvasTappableAt

```go
func AssertCanvasTappableAt(t *testing.T, c fyne.Canvas, pos fyne.Position) bool
```
AssertCanvasTappableAt asserts that the canvas is tappable at the given position.

#### func  AssertImageMatches

```go
func AssertImageMatches(t *testing.T, masterFilename string, img image.Image, msgAndArgs ...any) bool
```
AssertImageMatches asserts that the given image is the same as the one stored in the master file. The master filename is relative to the `testdata` directory which is relative to the test. The test `t` fails if the given image is not equal to the loaded master image. In this case the given image is written into a file in `testdata/failed/<masterFilename>` (relative to the test). This path is also reported, thus the file can be used as new master.

#### func  AssertNotificationSent

```go
func AssertNotificationSent(t *testing.T, n *fyne.Notification, f func())
```
AssertNotificationSent allows an app developer to assert that a notification was sent. After the content of f has executed this utility will check that the specified notification was sent.

#### func  AssertObjectRendersToImage

```go
func AssertObjectRendersToImage(t *testing.T, masterFilename string, o fyne.CanvasObject, msgAndArgs ...any) bool
```
AssertObjectRendersToImage asserts that the given `CanvasObject` renders the same image as the one stored in the master file. The theme used is the standard test theme which may look different to how it shows on your device. The master filename is relative to the `testdata` directory which is relative to the test. The test `t` fails if the given image is not equal to the loaded master image. In this case the given image is written into a file in `testdata/failed/<masterFilename>` (relative to the test). This path is also reported, thus the file can be used as new master.

Since 2.3

#### func  AssertObjectRendersToMarkup

```go
func AssertObjectRendersToMarkup(t *testing.T, masterFilename string, o fyne.CanvasObject, msgAndArgs ...any) bool
```
AssertObjectRendersToMarkup asserts that the given `CanvasObject` renders the same markup as the one stored in the master file. The master filename is relative to the `testdata` directory which is relative to the test. The test `t` fails if the rendered markup is not equal to the loaded master markup. In this case the rendered markup is written into a file in `testdata/failed/<masterFilename>` (relative to the test). This path is also reported, thus the file can be used as new master.

Be aware, that the indentation has to use tab characters ('\t') instead of spaces. Every element starts on a new line indented one more than its parent. Closing elements stand on their own line, too, using the same indentation as the opening element. The only exception to this are text elements which do not contain line breaks unless the text includes them.

Since 2.3

#### func  AssertRendersToImage

```go
func AssertRendersToImage(t *testing.T, masterFilename string, c fyne.Canvas, msgAndArgs ...any) bool
```
AssertRendersToImage asserts that the given canvas renders the same image as the one stored in the master file. The master filename is relative to the `testdata` directory which is relative to the test. The test `t` fails if the given image is not equal to the loaded master image. In this case the given image is written into a file in `testdata/failed/<masterFilename>` (relative to the test). This path is also reported, thus the file can be used as new master.

Since 2.3

#### func  AssertRendersToMarkup

```go
func AssertRendersToMarkup(t *testing.T, masterFilename string, c fyne.Canvas, msgAndArgs ...any) bool
```
AssertRendersToMarkup asserts that the given canvas renders the same markup as the one stored in the master file. The master filename is relative to the `testdata` directory which is relative to the test. The test `t` fails if the rendered markup is not equal to the loaded master markup. In this case the rendered markup is written into a file in `testdata/failed/<masterFilename>` (relative to the test). This path is also reported, thus the file can be used as new master.

Be aware, that the indentation has to use tab characters ('\t') instead of spaces. Every element starts on a new line indented one more than its parent. Closing elements stand on their own line, too, using the same indentation as the opening element. The only exception to this are text elements which do not contain line breaks unless the text includes them.


<div class="since">Since: <code>
2.0</code></div>

#### func  Canvas

```go
func Canvas() fyne.Canvas
```
Canvas returns a reusable in-memory canvas used for testing

#### func  DoubleTap

```go
func DoubleTap(obj fyne.DoubleTappable)
```
DoubleTap simulates a double left mouse click on the specified object.

#### func  Drag

```go
func Drag(c fyne.Canvas, pos fyne.Position, deltaX, deltaY float32)
```
Drag drags at an absolute position on the canvas. deltaX/Y is the dragging distance: <0 for dragging up/left, >0 for dragging down/right.

#### func  FocusNext

```go
func FocusNext(c fyne.Canvas)
```
FocusNext focuses the next focusable on the canvas.

#### func  FocusPrevious

```go
func FocusPrevious(c fyne.Canvas)
```
FocusPrevious focuses the previous focusable on the canvas.

#### func  KnownThemeVariants

```go
func KnownThemeVariants() map[string]fyne.ThemeVariant
```
KnownThemeVariants returns the known theme variants mapped by a descriptive key.

#### func  LaidOutObjects

```go
func LaidOutObjects(o fyne.CanvasObject) (objects []fyne.CanvasObject)
```
LaidOutObjects returns all fyne.CanvasObject starting at the given fyne.CanvasObject which is laid out previously.

#### func  MoveMouse

```go
func MoveMouse(c fyne.Canvas, pos fyne.Position)
```
MoveMouse simulates a mouse movement to the given position.

#### func  NewApp

```go
func NewApp() fyne.App
```
NewApp returns a new dummy app used for testing. It loads a test driver which creates a virtual window in memory for testing.

#### func  NewClipboard

```go
func NewClipboard() fyne.Clipboard
```
NewClipboard returns a single use in-memory clipboard used for testing

#### func  NewDriver

```go
func NewDriver() fyne.Driver
```
NewDriver sets up and registers a new dummy driver for test purpose

#### func  NewDriverWithPainter

```go
func NewDriverWithPainter(painter SoftwarePainter) fyne.Driver
```
NewDriverWithPainter creates a new dummy driver that will pass the given painter to all canvases created

#### func  NewTempApp

```go
func NewTempApp(t testing.TB) fyne.App
```
NewTempApp returns a new dummy app and tears it down at the end of the test.


<div class="since">Since: <code>
2.5</code></div>

#### func  NewTempWindow

```go
func NewTempWindow(t testing.TB, content fyne.CanvasObject) fyne.Window
```
NewTempWindow creates and registers a new window for test purposes. This window will get removed automatically once the running test ends.


<div class="since">Since: <code>
2.5</code></div>

#### func  NewTheme

```go
func NewTheme() fyne.Theme
```
NewTheme returns a new test theme using quiet ugly colors.

#### func  NewWindow

```go
func NewWindow(content fyne.CanvasObject) fyne.Window
```
NewWindow creates and registers a new window for test purposes

#### func  RenderObjectToMarkup

```go
func RenderObjectToMarkup(o fyne.CanvasObject) string
```
RenderObjectToMarkup renders the given [fyne.io/fyne/v2.CanvasObject] to a markup string.


<div class="since">Since: <code>
2.6</code></div>

#### func  RenderToMarkup

```go
func RenderToMarkup(c fyne.Canvas) string
```
RenderToMarkup renders the given [fyne.io/fyne/v2.Canvas] to a markup string.


<div class="since">Since: <code>
2.6</code></div>

#### func  Scroll

```go
func Scroll(c fyne.Canvas, pos fyne.Position, deltaX, deltaY float32)
```
Scroll scrolls at an absolute position on the canvas. deltaX/Y is the scrolling distance: <0 for scrolling up/left, >0 for scrolling down/right.

#### func  Tap

```go
func Tap(obj fyne.Tappable)
```
Tap simulates a left mouse click on the specified object.

#### func  TapAt

```go
func TapAt(obj fyne.Tappable, pos fyne.Position)
```
TapAt simulates a left mouse click on the passed object at a specified place within it.

#### func  TapCanvas

```go
func TapCanvas(c fyne.Canvas, pos fyne.Position)
```
TapCanvas taps at an absolute position on the canvas.

#### func  TapSecondary

```go
func TapSecondary(obj fyne.SecondaryTappable)
```
TapSecondary simulates a right mouse click on the specified object.

#### func  TapSecondaryAt

```go
func TapSecondaryAt(obj fyne.SecondaryTappable, pos fyne.Position)
```
TapSecondaryAt simulates a right mouse click on the passed object at a specified place within it.

#### func  TempWidgetRenderer

```go
func TempWidgetRenderer(t *testing.T, wid fyne.Widget) fyne.WidgetRenderer
```
TempWidgetRenderer allows test scripts to gain access to the current renderer for a widget. This can be used for verifying correctness of rendered components for a widget in unit tests. The widget renderer is automatically destroyed when the test ends.


<div class="since">Since: <code>
2.5</code></div>

#### func  Theme

```go
func Theme() fyne.Theme
```
Theme returns a test theme useful for image based tests.

#### func  Type

```go
func Type(obj fyne.Focusable, chars string)
```
Type performs a series of key events to simulate typing of a value into the specified object. The focusable object will be focused before typing begins. The chars parameter will be input one rune at a time to the focused object.

#### func  TypeOnCanvas

```go
func TypeOnCanvas(c fyne.Canvas, chars string)
```
TypeOnCanvas is like the Type function but it passes the key events to the canvas object rather than a focusable widget.

#### func  WidgetRenderer

```go
func WidgetRenderer(wid fyne.Widget) fyne.WidgetRenderer
```
WidgetRenderer allows test scripts to gain access to the current renderer for a widget. This can be used for verifying correctness of rendered components for a widget in unit tests.

#### func  WithTestTheme

```go
func WithTestTheme(t *testing.T, f func())
```
WithTestTheme runs a function with the testTheme temporarily set.

#### types

 * [SoftwarePainter](softwarepainter.html)
 * [WindowlessCanvas](windowlesscanvas.html)
