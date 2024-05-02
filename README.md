lv2-gtk-ui-bridge
=================

lv2-gtk-ui-bridge is a special LV2 bundle that allows to use legacy LV2 Gtk2/3 UIs as LV2 X11 UIs.  
This increases the compatibility of such UIs to hosts that do not support the legacy UI types.

Because Gtk2/3 can often conflict with host function symbols (e.g. a Gtk4 host can't load Gtk3 libraries) the UI is loaded in a separate process.  
This means it is not possible to support LV2 instance access nor LV2 data access, which some UIs use for fancy fast graphs.

Dependencies
------------

To build this project the following libraries/packages are required:

 - gtk2
 - gtk3
 - lilv
 - lv2
 - make
 - pkg-config
 - x11

Under Debian-based systems these can be installed with:

```sh
sudo apt-get install libgtk2.0-dev libgtk-3-dev liblilv-dev lv2-dev libx11-dev
```

Install
-------

After a successful build, simply copy or symlink the `lv2-gtk-ui-bridge.lv2` bundle into any direction within the `LV2_PATH`.  
There is no `make install` step.