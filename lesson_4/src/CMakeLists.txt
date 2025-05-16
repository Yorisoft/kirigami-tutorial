add_executable(kirigami-hello_4)

ecm_add_qml_module(kirigami-hello_4
    URI
    org.kde.tutorial_4
)

target_sources(kirigami-hello_4
    PRIVATE
    main.cpp
)

ecm_target_qml_sources(kirigami-hello_4
    SOURCES
    Main.qml
)

target_link_libraries(kirigami-hello_4
    PRIVATE
    Qt6::Quick
    Qt6::Qml
    Qt6::Gui
    Qt6::QuickControls2
    Qt6::Widgets
    KF6::I18n
    KF6::CoreAddons
    KF6::IconThemes
)

install(TARGETS kirigami-hello_4 ${KDE_INSTALL_TARGETS_DEFAULT_ARGS})
