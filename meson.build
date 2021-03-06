project('io.elementary.initial-setup', 'vala', 'c')

add_global_arguments('-DGETTEXT_PACKAGE="' + meson.project_name() + '"', language:'c')
add_project_arguments(['--vapidir', join_paths(meson.current_source_dir(), 'vapi')], 
                      language: 'vala')

gnome = import('gnome')
i18n = import('i18n')

accountservice_dep = dependency('accountsservice')
glib_dep = dependency('glib-2.0')
gobject_dep = dependency('gobject-2.0')
gtk_dep = dependency('gtk+-3.0')
gee_dep = dependency('gee-0.8')
granite_dep = dependency('granite', version: '>=0.5')
json_glib_dep = dependency('json-glib-1.0')
xml2_dep = dependency('libxml-2.0')
gnome_keyboard_dep = dependency('libgnomekbd')
gnome_keyboard_ui_dep = meson.get_compiler('c').find_library('libgnomekbdui')
polkit_dep = dependency('polkit-gobject-1')
posix_dep = meson.get_compiler('vala').find_library('posix')
pwquality_dep = dependency('pwquality')

dependencies = [
    accountservice_dep,
    glib_dep,
    gobject_dep,
    gtk_dep,
    gee_dep,
    json_glib_dep,
    xml2_dep,
    gnome_keyboard_dep,
    gnome_keyboard_ui_dep,
    granite_dep,
    polkit_dep,
    posix_dep,
    pwquality_dep
]

asresources = gnome.compile_resources(
    'as-resources', 'data/' + meson.project_name() + '.gresource.xml',
    source_dir: 'data',
    c_name: 'as'
)

subdir('po')
subdir('src')
subdir('data')
