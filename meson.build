project(
	'wfplug-winshadows',
	'c',
	'cpp',
	version: '0.1',
	license: 'MIT',
	meson_version: '>=0.53.0',
	default_options: [
		'cpp_std=c++17',
		'c_std=c11',
		'warning_level=2',
		'werror=false',
	],
)

wayfire_api_inc  = include_directories('/usr/include/wayfire')
plugins_common_inc = include_directories('/usr/include')
wayfire_conf_inc = include_directories(['.'])

wayfire        = dependency('wayfire')
cairo          = dependency('cairo')
pango          = dependency('pango')
pangocairo     = dependency('pangocairo')
pixman         = dependency('pixman-1')
wlroots        = dependency('wlroots', version: ['>=0.16.0', '<0.17.0'])
wfconfig       = dependency('wf-config', version: ['>=0.7.0', '<0.8.0'])

metadata_dir_suffix = 'share/wayfire/metadata'
sysconfdir = join_paths(get_option('prefix'), get_option('sysconfdir'))
pkgdatadir = join_paths(get_option('prefix'), 'share', 'wayfire', 'protocols')

add_project_arguments(['-DWAYFIRE_PLUGIN'], language: ['cpp', 'c'])
add_project_arguments(['-DWLR_USE_UNSTABLE'], language: ['cpp', 'c'])
add_project_link_arguments(['-rdynamic'], language: 'cpp')

subdir('metadata')
subdir('src')
