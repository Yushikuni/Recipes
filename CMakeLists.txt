cmake_minimum_required(VERSION 3.10)
project(MyProject)

# Nastavení standardu C++
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Nalezení knihovny Pistache
find_package(Pistache REQUIRED)

# Nastavení zdrojových souborů
set(SOURCES
    src/main.cpp
    src/server.cpp
    src/utils/parser.cpp
)

# Nastavení hlavičkových souborů
set(HEADERS
    include/models/recipe.hpp
    include/models/user.hpp
    src/server.hpp
    src/utils/parser.hpp
)

# Přidání spustitelného souboru
add_executable(MyProject ${SOURCES} ${HEADERS})

# Přidání linkování knihovny Pistache
target_link_libraries(MyProject Pistache::Pistache)
