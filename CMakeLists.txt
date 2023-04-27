cmake_minimum_required(VERSION 3.14)

project(FIZZBUZZ)

set(NUM "1")

if (NOT LIMIT)
    set(LIMIT "100")
endif()

while ("${NUM}" LESS_EQUAL "${LIMIT}")
    set(STRING "")

    math(EXPR RESULT "${NUM} % 3")
    if ("${RESULT}" EQUAL "0")
        set(STRING "fizz")
    endif()

    math(EXPR RESULT "${NUM} % 5")
    if (RESULT EQUAL 0)
        set(STRING "${STRING}buzz")
    endif()

    if (STRING STREQUAL "")
        message("${NUM}")
    else ()
        message("${STRING}")
    endif()

    math(EXPR NUM "${NUM} + 1")
endwhile()
