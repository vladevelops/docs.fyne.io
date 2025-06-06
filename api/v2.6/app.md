---
layout: page
tags: [api]
title: Fyne API "fyne.App"
package: fyne.io/fyne/v2
---

# fyne.App
---
```go
import "fyne.io/fyne/v2"
```

## Usage

#### type App

```go
type App interface {
	// Create a new window for the application.
	// The first window to open is considered the "master" and when closed
	// the application will exit.
	NewWindow(title string) Window

	// Open a URL in the default browser application.
	OpenURL(url *url.URL) error

	// Icon returns the application icon, this is used in various ways
	// depending on operating system.
	// This is also the default icon for new windows.
	Icon() Resource

	// SetIcon sets the icon resource used for this application instance.
	SetIcon(Resource)

	// Run the application - this starts the event loop and waits until [App.Quit]
	// is called or the last window closes.
	// This should be called near the end of a main() function as it will block.
	Run()

	// Calling Quit on the application will cause the application to exit
	// cleanly, closing all open windows.
	// This function does no thing on a mobile device as the application lifecycle is
	// managed by the operating system.
	Quit()

	// Driver returns the driver that is rendering this application.
	// Typically not needed for day to day work, mostly internal functionality.
	Driver() Driver

	// UniqueID returns the application unique identifier, if set.
	// This must be set for use of the [App.Preferences]. see [NewWithID].
	UniqueID() string

	// SendNotification sends a system notification that will be displayed in the operating system's notification area.
	SendNotification(*Notification)

	// Settings return the globally set settings, determining theme and so on.
	Settings() Settings

	// Preferences returns the application preferences, used for storing configuration and state
	Preferences() Preferences

	// Storage returns a storage handler specific to this application.
	Storage() Storage

	// Lifecycle returns a type that allows apps to hook in to lifecycle events.
	//
	// Since: 2.1
	Lifecycle() Lifecycle

	// Metadata returns the application metadata that was set at compile time.
	// The items of metadata are available after "fyne package" or when running "go run"
	// Building with "go build" may cause this to be unavailable.
	//
	// Since: 2.2
	Metadata() AppMetadata

	// CloudProvider returns the current app cloud provider,
	// if one has been registered by the developer or chosen by the user.
	//
	// Since: 2.3
	CloudProvider() CloudProvider // get the (if any) configured provider

	// SetCloudProvider allows developers to specify how this application should integrate with cloud services.
	// See [fyne.io/cloud] package for implementation details.
	//
	// Since: 2.3
	SetCloudProvider(CloudProvider) // configure cloud for this app

	// Clipboard returns the system clipboard.
	//
	// Since: 2.6
	Clipboard() Clipboard
}
```

An App is the definition of a graphical application. Apps can have multiple windows, by default they will exit when all windows have been closed. This can be modified using SetMaster or SetCloseIntercept. To start an application you need to call Run somewhere in your main function. Alternatively use the [fyne.io/fyne/v2.Window.ShowAndRun] function for your main window.

#### func  CurrentApp

```go
func CurrentApp() App
```
CurrentApp returns the current application, for which there is only 1 per process.
