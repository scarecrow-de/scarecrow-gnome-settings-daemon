sources = files(
  'cc-wwan-device.c',
  'scsd-wwan-manager.c',
  'main.c'
)

deps = plugins_deps + [gio_dep, gcr_base_dep, mm_glib_dep, polkit_gobject_dep]

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

