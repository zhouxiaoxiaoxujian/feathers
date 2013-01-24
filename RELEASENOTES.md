# Feathers Release Notes

Noteworthy changes in official releases of [Feathers](http://feathersui.com/).

## 1.1.0 PRERELEASE

* Added ILayoutObject to support extra data for layouts to use.
* Added AnchorLayout for fluid layouts and relative positioning.
* All sub-components are created from factories and can receive custom names for theming.
* PopUpManager: Supports custom root to place pop-ups somewhere other than the stage.
* PickerList: supports prompt when no item is selected.
* ScreenNavigator: added hasScreen(), getScreen(), and getScreenIDs().
* ScrollContainer, List, GroupedList: better auto-sizing with a background skin.
* BitmapFontTextRenderer, Scale3Image, Scale9Image: option to turn off the use of a separate QuadBatch.
* Scroller/Button: better blocking of touches on children when scrolling with touch.
* TiledRowsLayout, TiledColumnsLayout: supports separate horizontal and vertical gaps.
* IVariableVirtualLayout: added function addToVariableVirtualCacheAtIndex() for more specific control over the cache of item dimensions. The following implementation can be added to existing classes to simulate the old behavior:

		public addToVariableVirtualCacheAtIndex(index:int, item:DisplayObject = null):void
		{
			this.resetVariableVirtualCache();
		}

* IVariableVirtualLayout: added function removeFromVariableVirtualCacheAtIndex() for more specific control over the cache of item dimensions. The following implementation can be added to existing classes to simulate the old behavior:

		public removeFromVariableVirtualCacheAtIndex(index:int, item:DisplayObject = null):void
		{
			this.resetVariableVirtualCache();
		}


## 1.0.0

No major API changes since 1.0.0 BETA. Mostly bug fixes and minor improvements.

* Fix for memory leaks in List, GroupedList, and ImageLoader
* PageIndicator properly handles ImageLoader or other IFeathersControl as symbol
* IGroupedListHeaderOrFooterRenderer extends IFeathersControl
* Header: fix for "middle" vertical alignment
* Updated for Starling Framework 1.3

## 1.0.0 BETA

Initial release. The following major changes happened in the last month or two leading to the beta.

* GTween library removed as a dependency. All animations switched to the Starling `Tween` class.
* as3-signals library removed as a dependency. Switched to Starling events.
* `TextInput`: supports swappable text editors, similar to the text renderers used for uneditable text. The default `StageTextTextEditor` uses `StageText` to allow text input, which is ideal for mobile. The `TextFieldTextEditor` uses a `TextField` of `TextFieldType.INPUT` instead, and it may be a better choice for desktop. A static function, `defaultTextEditorFactory`, has been added to `FeathersControl`.
* `TextInput`: now has events for focus in and out.
* Item renderers: Switched to `ImageLoader` for icon and accessory textures, which has a `source` property that supports `Texture` instances or `String` URLs to load textures from the web. Properties like `iconTextureField` and `accessoryTextureFunction` now have new names like `iconSourceField` and `accessorySourceFunction` because values other than textures are now allowed. Similarly, `iconImageFactory` and `accessoryImageFactory` have been renamed to `iconLoaderFactory` and `accessoryLoaderFactory`.
* Item renderers: accessory may be positioned. See `layoutOrder` and `accessoryPosition` properties.
* Added `dispose()` method to `AddedWatcher` so that theme resources like textures be disposed.
* Added `ScrollText` component to display text in an overlay on the native display list. Useful for long passages of text that may be too large to convert to a texture.
* `ScreenNavigator`: added events for transition start and complete.
* `ToggleSwitch`: `TRACK_LAYOUT_MODE_STRETCH` is now `TRACK_LAYOUT_MODE_ON_OFF`.
* `Slider`: `TRACK_LAYOUT_MODE_STRETCH` is now `TRACK_LAYOUT_MODE_MIN_MAX`.
* `ScrollBar`: `TRACK_LAYOUT_MODE_STRETCH` is now `TRACK_LAYOUT_MODE_MIN_MAX`.