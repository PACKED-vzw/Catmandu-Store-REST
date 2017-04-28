# NAME

Catmandu::Store::REST - Store/retrieve items from a JSON REST-API endpoint

# SYNOPSIS

    # From the command line
    $ catmandu export REST --id 1234 --base_url https://www.example.org/api/v1/books --query_string /page/1 to YAML
    
    # From a Catmandu Fix
    lookup_in_store(
      book_id,
      REST,
      base_url: https://www.example.org/api/v1/books,
      query_string: /page/1
    )

# DESCRIPTION

    # From a Catmandu Fix
    lookup_in_store(
      book_id,
      REST,
      base_url: https://www.example.org/api/v1/books,
      query_string: /page/1
    )

Uses a RESTful API as a [Catmandu::Store](http://librecat.org/Catmandu/#stores).

The module allows you to use a RESTful API that uses JSON as data format and uses the URL format
`[base_url]/[id][query_string]` as a _Store_ for _Catmandu_.

Retrieving (`GET`), adding (`POST`), updating (`PUT`) and deleting (`DELETE`) single items is
supported. Data must be provided as JSON by the API, and the API must accept JSON for `PUT`/`POST`
requests. The URL must be of the format `[base_url]/[id][query_string]`, where the `id`
is absent for `POST` requests.

# PARAMETERS

You must provide the `base_url` parameter.

- `base_url`

    base url of the API endpoint (the entire url before the ID) (e.g. _https://www.example.org/api/v1/books_).

- `query_string`

    an optional query string that comes behind the ID (e.g. _/page/1_ where the complete URL is
    _https://www.example.org/api/v1/books/1/page/1_).

# AUTHOR

Pieter De Praetere <pieter@packed.be>

# COPYRIGHT

Copyright 2017- PACKED vzw

# LICENSE

This library is free software; you can redistribute it and/or modify
it under the same terms as Perl itself.

# SEE ALSO
