set(base_examples
    woss-aloha-example
)
foreach(
  example
  ${base_examples}
)
  build_lib_example(
    NAME ${example}
    SOURCE_FILES ${example}.cc
    LIBRARIES_TO_LINK
      ${libinternet}
      ${libmobility}
      ${libstats}
      ${libapplications}
      ${libuan}
      ${libnetanim}
      ${libwoss-ns3}
      ${libuan-vector}
  )
endforeach()
