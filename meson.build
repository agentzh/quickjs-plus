version = run_command(
    'cat', files('VERSION.txt'),
  ).stdout().strip()

qjs_c_args = [
  '-DCONFIG_VERSION="' + version + '"',
  '-DCONFIG_BIGNUM',
]

qjs_sources = [
  'quickjs.c',
  'libregexp.c',
  'libunicode.c',
  'cutils.c',
  'quickjs-libc.c',
  'libbf.c',
]

quickjs = library('quickjs', qjs_sources,
  c_args: frida_component_cflags + qjs_c_args,
)

quickjs_dep = declare_dependency(
  include_directories: include_directories('.'),
)
