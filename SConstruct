"""The SConstruct file"""

name = 'kfather'
major = '1'
minor = '0'
libraries = []

# You should not need to modify anything below this line

import os

from freelan.build_tools import LibraryProject, Environment

env = Environment(ENV = os.environ.copy(), ARGUMENTS = ARGUMENTS)

project = LibraryProject(name, major, minor, libraries, Glob('src/*.cpp'))

build = env.FreelanProject(project)
install = env.FreelanProjectInstall(project)
documentation = env.FreelanProjectDocumentation(project)
indent = env.FreelanProjectIndent(project)
samples = env.SConscript('samples/SConscript', exports = 'env project')

env.Alias('build', build)
env.Alias('install', install)
env.Alias('doc', documentation)
env.Alias('indent', indent)
env.Alias('samples', samples)

env.Default(build)