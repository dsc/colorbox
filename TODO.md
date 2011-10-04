# todo

 - Replace single global configuration with instance-based model (using `jQuery.data`).
 - Update rel-chain when DOM changes (using `jQuery.live`).
 - Use namespaced events?
 - Alias the `closed` event to `close`, deprecating `closed`: the past-tense name is confusing (it fires at the *start* of the close method) and inconsistent (no other event is past-tense: `open` is not `opened`, `complete` is not `completed`).
 - Calling `evt.preventDefault()` in an event handler should stop:
     - `open`
     - `load`
     - `close`
 - `$.colorbox.resize()` should also update any inferred information (like '{total}' in `settings.current`).
 - `el.colorbox.remove()` should only effect lightboxes associated with elements in `el`.
 - Add methods w/ static version for each operating on the first lightbox created:
     - `settings()`:`Object` -- Getter for settings object (static version effects defaults)
     - `settings(s)`:`el` -- Setter for settings object (static version effects defaults)
     - `open(settings={})`:`el` -- Opens lightbox (convenience for passing `{ open: true }` in settings); if no lightboxes have been defined, it acts like `$.colorbox()`.
     - `isOpen()`:`Boolean` -- Whether element's associated lightbox is open. Static returns `true` if any lightbox is open.
     - `navigate(delta)`:`el` -- Navigates the lightbox forward `delta` images.
     - `slideshow(start=true, options={})`:`el` -- Reconfigures slideshow.
     - `slideshow.isRunning()`:`Boolean`
     - `slideshow.start()`:`Boolean`
     - `slideshow.stop()`:`Boolean`
 - Add options for:
     - `scale`, `scaleX`, `scaleY`: scales image size (but still limited by `maxWidth`, `maxHeight`); accepts either Number or `(val, key, $target) -> Number`
     - Group options with namespace objects: `slideshow`,  (ex.`slideshowAuto` == `slideshow.auto`)
     - Alias: `slideshow.enabled` == `slideshow`
     - `slideshowStoppedByNav`: whether slideshow advancement is stopped when user interacts with lightbox via `prev()`, `next()`



# todoc

 - Triggering a cbox event with a namespace also triggers its non-namespaced event (e.g., `cbox_next.user` also triggers `cbox_next`)
 - Calling `evt.preventDefault()` in an event handler should stop:
    - `next`
    - `prev`
    - `slideshow_start`
    - `slideshow_stop`
 - Add event hooks for:
    - `next`, `next.user`, `next.slideshow`
    - `prev`, `prev.user`, `prev.slideshow`
    - `slideshow_start`
    - `slideshow_stop`

