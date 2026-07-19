# SEMRush Formulas
SEMRush Formulas
Related Searches
=SUBSTITUTE(textjoin(", ",true,IMPORTDATA(concatenate("https://api.semrush.com/?type=phrase_related&key=e82701d7419f13d965571b0fa80651f3&export_columns=Ph&phrase=",D2,"&database=us&display_limit=5"))), "Keyword, ","")

Full Searches
=SUBSTITUTE(textjoin(", ",true,IMPORTDATA(concatenate("https://api.semrush.com/?type=phrase_fullsearch&key=e82701d7419f13d965571b0fa80651f3&export_columns=Ph&phrase=",D2,"&database=us&display_limit=5"))), "Keyword, ","")

Top Questions
=SUBSTITUTE(textjoin(", ",true,IMPORTDATA(concatenate("https://api.semrush.com/?type=phrase_questions&key=e82701d7419f13d965571b0fa80651f3&export_columns=Ph&phrase=",D2,"&database=us&display_limit=20"))), "Keyword, ","")	