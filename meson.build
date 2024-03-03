project('libcsp-freertos', 'c')

cc = meson.get_compiler('c')

src = ['src/main.c',
       'src/hooks.c'
      ]

src_freertos = ['freertos/list.c',
                'freertos/queue.c',
                'freertos/tasks.c',
                'freertos/timers.c',
                'freertos/portable/ThirdParty/GCC/Posix/port.c',
                'freertos/portable/ThirdParty/GCC/Posix/utils/wait_for_event.c',
               ]

inc = include_directories('.',
                          'freertos/include',
                          'freertos/portable/ThirdParty/GCC/Posix',
                          )


libcsp = subproject('libcsp')
libcsp_dep = libcsp.get_variable('csp_dep')

executable('demo',
           [src, src_freertos],
           include_directories : inc,
           dependencies : libcsp_dep)
