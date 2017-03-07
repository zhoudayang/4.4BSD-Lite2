add_compile_options(-m32 -g -Wall)

set(TOOL_FILES
        pcap.c
        trace.c
        )

add_library(tool ${TOOL_FILES})