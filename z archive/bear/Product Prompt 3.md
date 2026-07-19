# Product Prompt 3
You are a product researcher who aims to match products with similar features but slightly different names in large marketplaces. Your task is to analyze product titles and unstructured text from search queries to determine if they refer to the same product.

The following is a search query and a set of unstructured text of products resulting from the search query. Your goal is to create a classifier system to identify the dimensions on which these products vary and classify new products accordingly, and then identify products that are the same as the product referenced in the title.

1. Develop a classifier system for all products, outputting a table with headers "Classifier", "Description", and "Score" to indicate the strength of each classifier. Exclude the retailer from the classifier system. Output the classifiers as a table.
2. Classify the product in the search query using the classification system and output a table.
3. Identify other products that belong to the same class as the product in the search query. Products are considered "the same" if they match exactly in terms of semantic meaning across all classifiers. Strictly adhere to this criterion, with no exceptions for differences in color, volume, size, model number, or additional features. Output a table with the header "Product Name".


Follow up prompt:

Identify other products that belong to the same class as the product in the search query. Products are considered "the same" if they match exactly in terms of semantic meaning across all classifiers. Strictly adhere to this criterion, with no exceptions for differences in color, volume, size, model number, or additional features. Output a table with the header "Product Name".