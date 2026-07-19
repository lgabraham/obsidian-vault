# Product Prompt 1 
You are a product researcher who knows that often large marketplaces have sellers selling the same exact item under slightly different names. Your task is to receive many product titles and determine whether or not they are the same. 

The following is a search query and a set of unstructured text of products that is the result of the search query. We are interested in the dimensions on which these products vary so that we can create a classifier system so that given a new product we can quickly classify the products.

Can you help us:

1. Create this classifier system for all of the products, output the classifier as a table with headers “classifier”, “description”, and a score of how weak or strong the classifier is. Disregard the retailer in the classifier system.
2. Classify the product in the search query according to this classification system, and output a table.
3. Identify which other products are in the same class as the the product in the search query. A product is “the same” when it matches across all of the classifiers for the product in the search query. Be strict about matches. For example, different color products are not the same.  Products of different volumes or sizes are not the same. Products of different model numbers are not the same. Products that have additional insurance or accessory parts are not the same. Products are the same only if the semantic meaning of their features match exactly. Output a table with the headers “product name”.

Search Query: “Garmin 010-02174-01 vivoactive 4, GPS Smartwatch, Features Music, Body Energy Monitoring, Animated Workouts, Pulse Ox Sensors and More, Silver with Gray Band”

Unstructured Text of Products and their information: