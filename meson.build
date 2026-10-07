# project name, programming language, and required meson version
project('io.github.dwmadden70.Vala',
    'vala', 'c',
    meson_version: '>=0.60.0'
)

gtk4_dep = dependency('gtk4')
glib_dep = dependency('glib-2.0')
gobject_dep = dependency('gobject-2.0')

# Create a new executable, list the files we want to compile, list the dependencies we need, and install
executable(
    meson.project_name(),
    'source' / 'application.vala',
    dependencies: [
        gtk4_dep, glib_dep, gobject_dep
    ],
    install: true
)

# Install our .desktop file so the Applications Menu will see it
install_data(
    'data' / 'application.desktop',
    install_dir: get_option('datadir') / 'applications',
    rename: meson.project_name() + '.desktop'
)

# Install our .metainfo.xml file so AppCenter will see it
install_data(
    'data' / 'appolication.metainfo.xml',
    install_dir: get_option('datadir') / 'metainfo',
    rename: meson.project_name() + 'metainfo.xml'
)