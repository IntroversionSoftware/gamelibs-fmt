project('fmt', 'cpp',
    default_options: [
        'buildtype=debugoptimized',
        'cpp_std=c++20',
        'cpp_rtti=false',
        'cpp_eh=none'
    ],
    version: '10.2.0'
)

compiler = meson.get_compiler('cpp')
link_deps = []

incdirs = ['include']
c_flags = []

sources = [
  'src/format.cc',
  'src/os.cc',
]

incdirs = include_directories(incdirs)

fmt_lib = library(
    'fmt',
    sources,
    cpp_args: c_flags,
    include_directories: incdirs,
    dependencies: link_deps,
)

fmt_dep = declare_dependency(
    compile_args: c_flags,
    include_directories: incdirs,
    dependencies: link_deps,
    link_with: fmt_lib,
    version: meson.project_version()
)

meson.override_dependency('fmt', fmt_dep)

# vim: set ts=4 sts=4 sw=4 et:
