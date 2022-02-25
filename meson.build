project('fmt', 'cpp',
    default_options: [
        'buildtype=debugoptimized',
        'cpp_std=c++2a',
        'cpp_rtti=false',
        'cpp_eh=none'
    ]
)

compiler = meson.get_compiler('cpp')
link_deps = []

incdirs = ['include']
cflags = []

sources = [
  'src/format.cc',
  'src/os.cc',
]

incdirs = include_directories(incdirs)

fmt = static_library(
    'fmt',
    sources,
    cpp_args: cflags,
    include_directories: incdirs,
    dependencies: link_deps,
)
fmt_dep = declare_dependency(
    include_directories: incdirs,
    dependencies: link_deps,
    link_with: fmt,
    version: meson.project_version()
)

meson.override_dependency('fmt', fmt_dep)

# vim: set ts=4 sts=4 sw=4 et:
