# Add configuration for building the `po` files
set(PO_FILES
    bg.po
    ca.po
    cs.po
    da.po
    de.po
    eo.po
    es.po
    eu.po
    fi.po
    fr.po
    ga.po
    gl.po
    hr.po
    hu.po
    id.po
    is.po
    it.po
    ja.po
    ka.po
    ko.po
    ms.po
    nb.po
    nl.po
    pl.po
    pt.po
    pt_BR.po
    ro.po
    ru.po
    sk.po
    sl.po
    sq.po
    sr.po
    sv.po
    tr.po
    uk.po
    vi.po
    zh_CN.po
    zh_TW.po
)

# Add source files for the `po` files
foreach(PO_FILE ${PO_FILES})
    add_custom_command(
        OUTPUT ${CMAKE_CURRENT_BINARY_DIR}/${PO_FILE}
        COMMAND ${CMAKE_COMMAND} -E copy ${CMAKE_CURRENT_SOURCE_DIR}/${PO_FILE} ${CMAKE_CURRENT_BINARY_DIR}/${PO_FILE}
        DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/${PO_FILE}
    )
endforeach()

add_custom_target(po ALL DEPENDS ${PO_FILES})
