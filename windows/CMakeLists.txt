cmake_minimum_required(VERSION 3.5)
project(freetype)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}/../include")

set(FT_INCLUDES ${CMAKE_CURRENT_SOURCE_DIR}/../include/ft2build.h
                ${CMAKE_CURRENT_SOURCE_DIR}/../include/freetype/config/ftconfig.h
                ${CMAKE_CURRENT_SOURCE_DIR}/../include/freetype/config/ftheader.h
                ${CMAKE_CURRENT_SOURCE_DIR}/../include/freetype/config/ftoption.h
                ${CMAKE_CURRENT_SOURCE_DIR}/../include/freetype/config/ftstdlib.h)

set(FT_SOURCES  ${CMAKE_CURRENT_SOURCE_DIR}/../src/autofit/autofit.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/bdf/bdf.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/cff/cff.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftbase.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftbitmap.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/cache/ftcache.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftdebug.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftfstype.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftgasp.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftglyph.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/gzip/ftgzip.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftinit.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/lzw/ftlzw.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftstroke.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftsystem.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/smooth/smooth.c)

set(FT_MODULES  ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftbbox.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftfntfmt.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftgxval.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftlcdfil.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftmm.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftotval.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftpatent.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftpfr.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftsynth.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/fttype1.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/base/ftwinfnt.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/pcf/pcf.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/pfr/pfr.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/psaux/psaux.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/pshinter/pshinter.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/psnames/psmodule.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/raster/raster.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/sfnt/sfnt.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/truetype/truetype.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/type1/type1.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/cid/type1cid.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/type42/type42.c
                ${CMAKE_CURRENT_SOURCE_DIR}/../src/winfonts/winfnt.c)

source_group("Source Files\\FT_MODULES\\" FILES ${FT_MODULES})

add_library(freetype SHARED ${FT_INCLUDES} ${FT_SOURCES} ${FT_MODULES})

target_compile_definitions(freetype PRIVATE "FT2_BUILD_LIBRARY")


