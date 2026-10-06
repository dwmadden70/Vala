project('elementary', 'vala', 'c')

gtk4_dep = dependency('gtk4')
glib_dep = dependency('glib-2.0')
gobject_dep = dependency('gobject-2.0')

executable('application',
    'source/application.vala',
    dependencies: [gtk4_dep, glib_dep, gobject_dep],
    install: true
)