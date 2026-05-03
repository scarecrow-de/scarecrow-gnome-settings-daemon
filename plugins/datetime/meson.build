install_data(
  'backward',
  install_dir: join_paths(scsd_pkgdatadir, 'datetime')
)

sources = files(
  'scsd-datetime-manager.c',
  'scsd-timezone-monitor.c',
  'main.c',
  'tz.c',
  'weather-tz.c'
)

sources += gnome.gdbus_codegen(
  'timedated',
  'timedated1-interface.xml',
  interface_prefix: 'org.freedesktop.'
)

deps = plugins_deps + [
  geocode_glib_dep,
  gweather_dep,
  libgeoclue_dep,
  libnotify_dep,
  m_dep,
  polkit_gobject_dep
]

cflags += ['-DGNOMECC_DATA_DIR="@0@"'.format(scsd_pkgdatadir)]

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
