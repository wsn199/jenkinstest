# CMakeのバージョンを設定
cmake_minimum_required(VERSION 3.10.2)
# プロジェクト名と使用する言語を設定
project(unitTest_cmake C)


include_directories(./add/include)

# unitTest.outという実行ファイルをadd.cとunitTest.cから作成
add_executable(Main main.c add/src/add.c)


add_executable(UnitTest test/unitTest.c add/src/add.c)

# unitTest.out作成時に libcunit.aをリンク
target_link_libraries(UnitTest cunit)


