# Add configuration for building documentation
set(DOC_FILES
    cheatsheet.html
    faq.html
    nano.1
    nanorc.5
    rnano.1
    sample.nanorc.in
)

# Add target for generating HTML and man pages
add_custom_target(doc ALL
    DEPENDS ${DOC_FILES}
    COMMAND groff -t -mandoc -Thtml < nano.1 > nano.1.html
    COMMAND groff -t -mandoc -Thtml < nanorc.5 > nanorc.5.html
    COMMAND groff -t -mandoc -Thtml < rnano.1 > rnano.1.html
)

install(FILES ${DOC_FILES} DESTINATION ${CMAKE_INSTALL_DOCDIR})
