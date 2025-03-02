project(
  'my_init', ['c','cpp'],
  version : '0.1',
  default_options : [
    'buildtype=debugoptimized',
    'cpp_std=c++17',
    'warning_level=1',
  ])

compiler = meson.get_compiler('cpp')
glmDep = dependency('glm')

libsPath = '/usr/lib/x86_64-linux-gnu/'
if not glmDep.found()
  glmDep = compiler.find_library('glm', dirs: libsPath)
endif

my_project_name = meson.current_source_dir().split('/').get(-1)

src_files = [
  'src/main.cpp',
]

#  meson.project_name(),   이렇게 하면됨 (겁나 간단함)

inc = include_directories('include')

executable(my_project_name, src_files,
          include_directories : inc,
          dependencies: [glmDep, 
                        ])
