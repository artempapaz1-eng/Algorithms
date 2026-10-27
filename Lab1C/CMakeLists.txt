add_executable(task task.cpp)
target_include_directories(task PRIVATE ${CMAKE_SOURCE_DIR}/LibraryCPP)
target_link_libraries(task LibraryCPP)

# Test 1: Базовый пример из задания (3x3 со стенами)
add_test(
    NAME test1_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test1_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test1_output.txt
)
add_test(
    NAME test1_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test1_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test1_expected.txt
)
set_tests_properties(test1_check PROPERTIES DEPENDS test1_run)

# Test 2: Прямоугольный лабиринт 3x4
add_test(
    NAME test2_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test2_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test2_output.txt
)
add_test(
    NAME test2_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test2_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test2_expected.txt
)
set_tests_properties(test2_check PROPERTIES DEPENDS test2_run)

# Test 3: Соседние клетки (старт сразу рядом с финишем)
add_test(
    NAME test3_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test3_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test3_output.txt
)
add_test(
    NAME test3_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test3_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test3_expected.txt
)
set_tests_properties(test3_check PROPERTIES DEPENDS test3_run)

# Test 4: Извилистый лабиринт 4x5 с обходом стен
add_test(
    NAME test4_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test4_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test4_output.txt
)
add_test(
    NAME test4_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test4_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test4_expected.txt
)
set_tests_properties(test4_check PROPERTIES DEPENDS test4_run)

# Test 5: Непроходимый лабиринт (стены полностью блокируют путь)
add_test(
    NAME test5_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test5_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test5_output.txt
)
add_test(
    NAME test5_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test5_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test5_expected.txt
)
set_tests_properties(test5_check PROPERTIES DEPENDS test5_run)

# Test 6: Одномерный горизонтальный коридор 1x5
add_test(
    NAME test6_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test6_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test6_output.txt
)
add_test(
    NAME test6_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test6_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test6_expected.txt
)
set_tests_properties(test6_check PROPERTIES DEPENDS test6_run)

# Test 7: Развилка с тупиковым коридором (ветвление: одна ветка в тупик, вторая к финишу)
add_test(
    NAME test7_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test7_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test7_output.txt
)
add_test(
    NAME test7_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test7_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test7_expected.txt
)
set_tests_properties(test7_check PROPERTIES DEPENDS test7_run)

# Test 8: Развилка с выбором кратчайшего пути (два пути разной длины: длинный в обход и короткий прямой)
add_test(
    NAME test8_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test8_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test8_output.txt
)
add_test(
    NAME test8_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test8_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test8_expected.txt
)
set_tests_properties(test8_check PROPERTIES DEPENDS test8_run)

# Test 9: Несколько последовательных развилок с тупиковыми ответвлениями (дерево развилок)
add_test(
    NAME test9_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test9_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test9_output.txt
)
add_test(
    NAME test9_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test9_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test9_expected.txt
)
set_tests_properties(test9_check PROPERTIES DEPENDS test9_run)

# Test 10: Перекрёсток с многолучевой развилкой (тупики в разные стороны и один выход)
add_test(
    NAME test10_run
    COMMAND task
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test10_input.txt
            ${CMAKE_CURRENT_BINARY_DIR}/test10_output.txt
)
add_test(
    NAME test10_check
    COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
            ${CMAKE_CURRENT_BINARY_DIR}/test10_output.txt
            ${CMAKE_CURRENT_SOURCE_DIR}/tests/test10_expected.txt
)
set_tests_properties(test10_check PROPERTIES DEPENDS test10_run)
