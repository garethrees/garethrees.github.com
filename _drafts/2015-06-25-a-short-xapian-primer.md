---
layout: post
title: A Short Xapian Primer
---

# {{ page.title }}

[Xapian](http://xapian.org) is an open source search engine library. It's got bindings for plenty of modern languages.

## Databases

Xapian stores its indexed documents in a database. Xapian has a few different [backends](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/databases.html#backends), but the default – Chert – stores information on the filesystem. From this point, assume I'm talking about Chert unless otherwise stated.

    $ ls -1 xapiandbs/development
    flintlock
    iamchert
    position.DB
    position.baseA
    position.baseB
    postlist.DB
    postlist.baseA
    postlist.baseB
    record.DB
    record.baseA
    record.baseB
    spelling.DB
    spelling.baseA
    spelling.baseB
    termlist.DB
    termlist.baseA
    termlist.baseB

Xapian has options for reliability and scalability, like [remote databases](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/databases.html#remote-databases-and-replication) and searching [multiple databases](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/databases.html#stub-database-files) at once then combining the results.

All backends only support a **single writer**. Multiple concurrent readers are supported. There are a few things to take in to account for [concurrent access](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/databases.html#concurrent-access). A lock is obtained on the database when it is opened by a writer, preventing any other processes writing to the database.

## Documents

Like many other search engines, documents are the core concept of Xapian. Each document has a unique _document ID_.

Documents have three components: _data_, _terms_ and _values_.

### Data

[Document _data_](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/documents.html#document-data) is <q>an arbitrary binary blob of data associated with the document.</q> Xapian doesn't do anything with this data – it just returns it when requested. Its most useful for storing information needed to display the search results. This could be an ID and type of record in your database (`Product-376`) or some serialized (JSON, YAML, Key-Value – Xapian doesn't care) summary information.

### Terms

A [document's terms](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/terms.html#terms) contain all the terms that a query might match. Xapian has a [term generator](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/termgenerator.html) which parses your text to produce appropriate terms. The terms generated are usually normalised with [stemming](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/terms.html#stemmers) stemming applied, so they might look a bit odd. This helps the search to find closely related words.

### Values

[Values](http://getting-started-with-xapian.readthedocs.org/en/latest/concepts/indexing/values.html) are pieces of data that can be used during a search.

> These pieces of data could be things such as keys which you want to be able to sort the results on, numeric values used for range searches, or numbers to be used to affect the weight calculated for documents during the search.

Values are stored in numbered slots. For example, in a database indexing recipes the value slots may contain something like:

    [0] indian  # The type of cuisine
    [1] mild    # The spiciness of the dish
    [2] 30      # The time in minutes needed to make the meal

You can map these slots to human-readable keys in your program.

    value_mappings = {
      0 => 'category',
      1 => 'heat',
      2 => 'time'
    }

The keys can be used in search queries:

    query = 'Chicken Jalfrezi category:indian'

The more data that has to be read from values the slower the search will be, so its a good idea to keep the amount of data stored in values to a minimum.

TODO: What data types can be stored in values?

---

#### Fields

Fields are 'special' terms that can be used to filter documents. Fields can be actual fields from a document (e.g. "title") or metadata about the document (e.g. "")







