libswresample_majorver = '3'
minorver = '2'
microver = '100'

libswresample_version = libswresample_majorver + '.' + minorver + '.' + microver

libswresample_sources = files([
  'audioconvert.c',
  'dither.c',
  'options.c',
  'rematrix.c',
  'resample.c',
  'resample_dsp.c',
  'swresample.c',
  'swresample_frame.c',
])

libswresample_optional_sources = {
  'libsoxr' : files('soxr_resample.c'),
  'shared' : files('log2_tab.c'),
}

libswresample_tests = [
  ['swresample', files(['tests/swresample.c'])],
]

# Version file
ver_conf = configuration_data()
ver_conf.set('majorver', libswresample_majorver)
ver_conf.set('minorver', minorver)
ver_conf.set('microver', microver)

configure_file(
  input: 'version.h.in',
  output: 'version.h',
  configuration: ver_conf,
)

configure_file(
  input: 'libswresample.v.in',
  output: 'libswresample.ver',
  configuration: ver_conf,
)

subdir('x86')
