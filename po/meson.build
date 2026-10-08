# Guard: only enable gettext if at least one .po file exists

fs = import('fs')

po_files = []
linguas = fs.read('LINGUAS').strip().split(' ')
foreach lang : linguas
  if fs.is_file(lang + '.po')
    po_files += [lang + '.po']
  endif
endforeach

if po_files.length() > 0
  i18n.gettext(meson.project_name(),
    args: '--directory=' + meson.project_source_root(),
    preset: 'glib'
  )
endif

i18n.gettext(meson.project_name(), preset: 'glib')