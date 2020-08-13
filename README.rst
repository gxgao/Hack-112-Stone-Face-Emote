This was a team project under the name Stone-Face-Emoji completed for the Hack 112 competition at Carnegie Mellon University. The project placed 2nd in the awards ceremony. 

Contributors: 
George Gao
Shivank Joshi
Bryce Yeazell

The project's goal was to analyze a given excerpt and then tell the user what genre that excerpt came from. 

The project ran in 3 parts. 
The first part was webscraping. This was handled by me (George). The code simply ran through a website gathering excerpts from books of popular genres and assimulated them into a text file. This was done with the help of selenium, beautiful soup, and requests. 

The second part handled processing all the data to build a database for each genre of a book and was handled mostly by Shivank. He used TextBlob to read and analyze the excerpts and assigned 'scores' to each excerpt based on a few different catagories such as gramatical syntax, sentence structure, etc. He stored the scores in a seperate text file. 

The final part, the UI was designed by Bryce. We used a graphics module designed by Carnegie Mellon University. It prompts users to enter an excerpt, and would return an image, as well as a guess as to which genre the excerpt had came from. Updated UX was done by me (George) to bug fix some UI problems. 

To run the code now, the user only needs to interact with the UI portion, which is found under the python file: UX.py. The other files are setup, and data. 
To use the code, run UX.py. Click the program. It will prompt you to enter a possible excerpt into the terminal. Once done press enter, the app should automatically update with the result. To quit the program close out or press e. 

We used a multitude of modules for the project one of which is TextBlob. The TextBlob ReadMe is found below.


TextBlob: Simplified Text Processing
====================================

.. image:: https://badgen.net/pypi/v/TextBlob
    :target: https://pypi.org/project/textblob/
    :alt: Latest version

.. image:: https://badgen.net/travis/sloria/TextBlob/dev
    :target: https://travis-ci.org/sloria/TextBlob
    :alt: Travis-CI

Homepage: `https://textblob.readthedocs.io/ <https://textblob.readthedocs.io/>`_

`TextBlob` is a Python (2 and 3) library for processing textual data. It provides a simple API for diving into common natural language processing (NLP) tasks such as part-of-speech tagging, noun phrase extraction, sentiment analysis, classification, translation, and more.


.. code-block:: python

    from textblob import TextBlob

    text = '''
    The titular threat of The Blob has always struck me as the ultimate movie
    monster: an insatiably hungry, amoeba-like mass able to penetrate
    virtually any safeguard, capable of--as a doomed doctor chillingly
    describes it--"assimilating flesh on contact.
    Snide comparisons to gelatin be damned, it's a concept with the most
    devastating of potential consequences, not unlike the grey goo scenario
    proposed by technological theorists fearful of
    artificial intelligence run rampant.
    '''

    blob = TextBlob(text)
    blob.tags           # [('The', 'DT'), ('titular', 'JJ'),
                        #  ('threat', 'NN'), ('of', 'IN'), ...]

    blob.noun_phrases   # WordList(['titular threat', 'blob',
                        #            'ultimate movie monster',
                        #            'amoeba-like mass', ...])

    for sentence in blob.sentences:
        print(sentence.sentiment.polarity)
    # 0.060
    # -0.341

    blob.translate(to="es")  # 'La amenaza titular de The Blob...'

TextBlob stands on the giant shoulders of `NLTK`_ and `pattern`_, and plays nicely with both.

Features
--------

- Noun phrase extraction
- Part-of-speech tagging
- Sentiment analysis
- Classification (Naive Bayes, Decision Tree)
- Language translation and detection powered by Google Translate
- Tokenization (splitting text into words and sentences)
- Word and phrase frequencies
- Parsing
- `n`-grams
- Word inflection (pluralization and singularization) and lemmatization
- Spelling correction
- Add new models or languages through extensions
- WordNet integration

Get it now
----------
::

    $ pip install -U textblob
    $ python -m textblob.download_corpora

Examples
--------

See more examples at the `Quickstart guide`_.

.. _`Quickstart guide`: https://textblob.readthedocs.io/en/latest/quickstart.html#quickstart


Documentation
-------------

Full documentation is available at https://textblob.readthedocs.io/.

Requirements
------------

- Python >= 2.7 or >= 3.4

Project Links
-------------

- Docs: https://textblob.readthedocs.io/
- Changelog: https://textblob.readthedocs.io/en/latest/changelog.html
- PyPI: https://pypi.python.org/pypi/TextBlob
- Issues: https://github.com/sloria/TextBlob/issues

License
-------

MIT licensed. See the bundled `LICENSE <https://github.com/sloria/TextBlob/blob/master/LICENSE>`_ file for more details.

.. _pattern: http://www.clips.ua.ac.be/pattern
.. _NLTK: http://nltk.org/
