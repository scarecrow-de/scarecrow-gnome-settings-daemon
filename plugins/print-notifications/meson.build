sources = files(
  'scsd-print-notifications-manager.c',
  'main.c'
)

deps = plugins_deps + [
  cups_dep,
  gtk_dep,
  libnotify_dep
]

cflags += ['-DLIBEXECDIR="@0@"'.format(scsd_libexecdir)]
cflags += ['-DBINDIR="@0@"'.format(scsd_bindir)]

executable(
  'scsd-' + plugin_name,
  sources,
  include_directories: [top_inc, common_inc],
  dependencies: deps,
  c_args: cflags,
  install: true,
  install_rpath: scsd_pkglibdir,
  install_dir: scsd_libexecdir
)

program = 'scsd-printer'

executable(
  program,
  program + '.c',
  include_directories: top_inc,
  dependencies: deps,
  c_args: '-DGNOME_SETTINGS_LOCALEDIR="@0@"'.format(scsd_localedir),
  install: true,
  install_rpath: scsd_pkglibdir,
  install_dir: scsd_libexecdir
)
