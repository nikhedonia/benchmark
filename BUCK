macos_flags = [
  '-DHAVE_STD_REGEX',
]

linux_flags = [
  '-DHAVE_POSIX_REGEX',
]

cxx_library(
  name = 'benchmark',
  header_namespace = 'benchmark',
  exported_headers = subdir_glob([
    ('include/benchmark', '*.h'),
  ]),
  headers = subdir_glob([
    ('src', '*.h'),
  ]),
  srcs = glob([
    'src/*.cc',
  ]),
  compiler_flags = [
    '-std=c++14',
  ],
  platform_compiler_flags = [
    ('default', macos_flags),
    ('^macos.*', macos_flags),
    ('^linux.*', linux_flags),
  ],
  exported_platform_linker_flags = [
    ('^linux.*', ['-lpthread'])
  ], 
  visibility = [
    'PUBLIC',
  ],
)
