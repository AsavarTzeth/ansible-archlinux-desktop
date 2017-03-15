Ansible GSettings Module - ansible-gsetting
===========================================

**Ansible module used for setting GSettings entries.**

##Installation

    curl -O https://raw.githubusercontent.com/AsavarTzeth/ansible-gsetting/master/gsetting

or clone the repository:

    git clone https://github.com/AsavarTzeth/ansible-gsetting.git

##Using the module

```
- name: disable audible bell
  gsetting:
    key: org.gnome.desktop.wm.preferences.audible-bell
    value: false

- name: shortcut panel-main-menu
  gsetting:
    key: org.gnome.desktop.wm.keybindings.panel-main-menu
    value: "@as []"

- name: input sources
  gsetting:
    key: org.gnome.desktop.input-sources.sources
    value: "[('xkb','se'),('xkb','us')]"

- name: scaling-factor for hidpi
  gsetting:
    key: org.gnome.desktop.interface.scaling-factor
    value: 'uint32 2'
```

Be mindful about string values, which should be passed into GSettings
single-quoted. You'll need to quote the value twice in YAML:

```
- name: nautilus use list view
  gsetting:
    key: org.gnome.nautilus.preferences.default-folder-viewer
    value: "'list-view'"

- name: nautilus list view columns
  gsetting:
    key: org.gnome.nautilus.list-view.default-visible-columns
    value: "['name','size','type','date_modified']"
```
