# CMakeの最低バージョンを指定
cmake_minimum_required(VERSION 3.29.0)

# プロジェクト名の設定
project(MyTestProject)

# C++の標準を指定（例：C++23）
set(CMAKE_CXX_STANDARD 23)

# GoogleTestをサブモジュールとして追加
#add_subdirectory(extern/googletest)

# ビルドタイプの設定
set(CMAKE_BUILD_TYPE Debug)

# メインのソースコードを指定（実行ファイル名 ソースファイル名）
#add_executable(SampleApp SampleApp.cpp)
add_library(SampleApp test/test_main.cpp)

# ヘッダファイルのインクルードパスを指定
include_directories(./gg/googletest)

# テスト用のソースファイルを指定
add_executable(test_my_class test/sample_test.cpp)

# GoogleTestライブラリをリンク
target_link_libraries(test_my_class gtest gtest_main)

# CMakeにテストを有効にするように指示
enable_testing()
