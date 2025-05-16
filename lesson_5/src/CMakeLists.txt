add_executable(kirigami-hello_5)

ecm_add_qml_module(kirigami-hello_5
    URI
    org.kde.tutorial_5
)

target_sources(kirigami-hello_5
    PRIVATE
    main.cpp
)

ecm_target_qml_sources(kirigami-hello_5
    SOURCES
    Main.qml
)

target_link_libraries(kirigami-hello_5
    PRIVATE
    Qt6::Quick
    Qt6::Qml
    Qt6::Gui
    Qt6::QuickControls2
    Qt6::Widgets
    KF6::I18n
    KF6::CoreAddons
    KF6::IconThemes
    kirigami-hello-components
)

install(TARGETS kirigami-hello_5 ${KDE_INSTALL_TARGETS_DEFAULT_ARGS})

add_subdirectory(components)
