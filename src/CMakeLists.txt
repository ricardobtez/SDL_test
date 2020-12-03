
find_package(PkgConfig REQUIRED)

pkg_check_modules(sdl2 REQUIRED sdl2)


# Generic test that uses conan libs
add_executable(SDL_APP main.cpp)
target_include_directories(SDL_APP PUBLIC ./ ${sdl2_INCLUDE_DIRS})
target_link_libraries(SDL_APP PRIVATE project_warnings project_options ${sdl2_LIBRARIES} ${sdl2_CFLAGS})
