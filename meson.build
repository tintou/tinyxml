project('tinyxml', 'cpp', version: '2.6.2')

pkg = import('pkgconfig')

extra_c_flags = []
if get_option('use_stl')
    extra_c_flags = ['-DTIXML_USE_STL=1']
    add_project_arguments(extra_c_flags, language: 'cpp')
endif

public_headers = ['tinyxml.h']

if not get_option('use_stl')
    public_headers += 'tinystr.h'
endif

install_headers(
    public_headers
)

lib = library(
    meson.project_name(),
    'tinyxml.cpp',
    'tinyxmlparser.cpp',
    'xmltest.cpp',
    'tinyxmlerror.cpp',
    'tinystr.cpp',
    version: meson.project_version(),
    install: true
)

pkg.generate(
    lib,
    filebase: 'tinyxml',
    name: 'TinyXml',
    description: 'Simple, small, C++ XML parser',
    extra_cflags: extra_c_flags
)
