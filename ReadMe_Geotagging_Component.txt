The geotagging component performs the following actions:
    1) extracts "location" entity from texts,
    2) determines geographic coordinates (latitude and longitude) based on locations,
    3) computes cell based on geographic coordinates.

Step 1) is implemented by the geoNLP project written in Java with Maven support. All external dependencies are specified in the pom.xml file. In particular, it uses Stanford CoreNLP library to extract "location" entity from texts. The input files should be named as "<name>_train.txt" or "<name>_test.txt". Each line is a JSON formatted string of the data returned by social networks API, plus an additional field "stream_type", which should be equal to "Twitter", "Instagram" or "YouTube". See "sample_train.txt" and "sample_test.txt" for examples of the input files. The program generates output files named as "<name>_nlp.txt".

Steps 2) and 3) are implemented in Python, file geocode.py. The input files should be named as "<name>_nlp.txt". The program will generate output files named as "<name>_geo.txt". geocode.py uses Google Maps Geocoding API, which requires an API key. Follow its documentation to get a key and specify it in the "config.json" file accordingly. Make sure that the key is specified in the configuration file before running the geocode.py program.
