cmake_minimum_required(VERSION 3.20)
project(kirigami-tutorial)

find_package(ECM 6.0.0 REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH})

include(KDEInstallDirs)
include(KDECMakeSettings)
include(KDECompilerSettings NO_POLICY_SCOPE)
include(ECMFindQmlModule)
include(ECMQmlModule)

find_package(Qt6 REQUIRED COMPONENTS
    Core
    Quick
    Test
    Gui
    QuickControls2
    Widgets
)

find_package(KF6 REQUIRED COMPONENTS
    Kirigami
    I18n
    CoreAddons
    QQC2DesktopStyle
    IconThemes
)

ecm_find_qmlmodule(org.kde.kirigami REQUIRED)

add_subdirectory(lesson_0/src)
add_subdirectory(lesson_1/src)
add_subdirectory(lesson_2/src)
add_subdirectory(lesson_3/src)

install(PROGRAMS 
    lesson_0/org.kde.tutorial.desktop 
    lesson_1/org.kde.tutorial.desktop 
    lesson_2/org.kde.tutorial.desktop 
    lesson_3/org.kde.tutorial.desktop 
    DESTINATION ${KDE_INSTALL_APPDIR}
)

feature_summary(WHAT ALL INCLUDE_QUIET_PACKAGES FATAL_ON_MISSING_REQUIRED_PACKAGES)
