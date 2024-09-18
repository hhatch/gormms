cmake_minimum_required (VERSION 3.5)
project (GORMS)
set (CMAKE_CXX_STANDARD 11)

# CMAKE plugins in the cmake directory
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_SOURCE_DIR}/sphinx)

find_package(Sphinx REQUIRED)

# set(SPHINX_THEME "nature")
set(SPHINX_THEME "sphinx_rtd_theme")

# configured documentation tools and intermediate build results
set(BINARY_BUILD_DIR "${CMAKE_CURRENT_BINARY_DIR}/_build")

# Sphinx cache with pickled ReST documents
set(SPHINX_CACHE_DIR "${CMAKE_CURRENT_BINARY_DIR}/_doctrees")

# HTML output directory
set(SPHINX_HTML_DIR "${CMAKE_CURRENT_BINARY_DIR}/html")

# LATEX output directory
set(SPHINX_LATEX_DIR "${CMAKE_CURRENT_BINARY_DIR}/latex")

# FEASST version
set(FEASST_VERSION ${GIT_COMMIT_HASH})

configure_file(
  "${CMAKE_SOURCE_DIR}/sphinx/conf.py.in"
  "${BINARY_BUILD_DIR}/conf.py"
  @ONLY)

# copy favicon, leave notice and extended layout
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_static/favicon.ico ${BINARY_BUILD_DIR}/favicon.ico COPYONLY)
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_static/leave_notice.js ${BINARY_BUILD_DIR}/_static/leave_notice.js COPYONLY)
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_templates/layout.html ${BINARY_BUILD_DIR}/_templates/layout.html COPYONLY)
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_templates/footer.html ${BINARY_BUILD_DIR}/_templates/footer.html COPYONLY)
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_templates/breadholder.html ${BINARY_BUILD_DIR}/_templates/breadholder.html COPYONLY)
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_templates/breadcrumbs.html ${BINARY_BUILD_DIR}/_templates/breadcrumbs.html COPYONLY)
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_templates/boilerplate-header.html ${BINARY_BUILD_DIR}/_templates/boilerplate-header.html COPYONLY)
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_templates/boilerplate-footer.html ${BINARY_BUILD_DIR}/_templates/boilerplate-footer.html COPYONLY)
configure_file(
  ${CMAKE_SOURCE_DIR}/sphinx/_build/_templates/searchbox.html ${BINARY_BUILD_DIR}/_templates/searchbox.html COPYONLY)

add_custom_target(html ALL
  ${SPHINX_EXECUTABLE}
      -q -b html
      -c "${BINARY_BUILD_DIR}"
      -d "${SPHINX_CACHE_DIR}"
      "../"
      "${SPHINX_HTML_DIR}"
  COMMENT "Building HTML documentation with Sphinx")

#add_custom_target(latex ALL
#  ${SPHINX_EXECUTABLE}
#      -q -b latex
#      -c "${BINARY_BUILD_DIR}"
#      -d "${SPHINX_CACHE_DIR}"
#      "../"
#      "${SPHINX_LATEX_DIR}"
#  COMMENT "Building LATEX documentation with Sphinx")
#
#add_custom_target(pdf ALL
#  ${CMAKE_COMMAND} -E chdir "${SPHINX_LATEX_DIR}" make
#  COMMENT "Building PDF from LATEX documentation with Sphinx")
#
#add_dependencies(pdf latex)

