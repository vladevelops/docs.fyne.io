---
layout: page
tags: [api]
title: Fyne API "fyne.Notification"
package: fyne.io/fyne/v2
---

# fyne.Notification
---
```go
import "fyne.io/fyne/v2"
```

## Usage

#### type Notification

```go
type Notification struct {
	Title, Content string
}
```

Notification represents a user notification that can be sent to the operating system.

#### func  NewNotification

```go
func NewNotification(title, content string) *Notification
```
NewNotification creates a notification that can be passed to [App.SendNotification].
