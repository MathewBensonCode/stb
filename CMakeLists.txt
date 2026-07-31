cmake_minimum_required(VERSION 3.25...4.4)

project(stb C)

add_library(stb INTERFACE)
add_library(std::stb ALIAS stb)

target_sources(
  stb
  INTERFACE FILE_SET
            HEADERS
            BASE_DIRS
            .
            FILES
            stb_c_lexer.h
            stb_connected_components.h
            stb_divide.h
            stb_ds.h
            stb_dxt.h
            stb_easy_font.h
            stb_herringbone_wang_tile.h
            stb_hexwave.h
            stb_image.h
            stb_image_resize2.h
            stb_image_write.h
            stb_include.h
            stb_leakcheck.h
            stb_perlin.h
            stb_rect_pack.h
            stb_sprintf.h
            stb_textedit.h
            stb_tilemap_editor.h
            stb_truetype.h
            stb_voxel_render.h)

install(TARGETS stb EXPORT stb-targets FILE_SET HEADERS DESTINATION include/stb)

install(EXPORT stb-targets DESTINATION lib/cmake/stb NAMESPACE stb:: FILE stbConfig.cmake)
