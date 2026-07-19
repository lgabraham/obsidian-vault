# Formula
=IFERROR(REGEXEXTRACT(REGEXREPLACE(IMPORTXML(a2, “*/script[@type=\’application/ld+json\’]/text()”), “\r\n|\n|\r”, “”), “””description””:””([^””]+)”), IMPORTXML(a2, “//meta[@property=\’og:description\’]*@content”))
