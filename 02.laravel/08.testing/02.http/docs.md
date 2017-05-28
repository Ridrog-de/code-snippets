---
title: HTTP Tests
published: true
date: '28-05-2017 11:24'
publish_date: '27-05-2017 16:39'
taxonomy:
    category:
        - docs
    tag:
        - laravel
    language:
        - php
    version:
        - '5.4'
    framework:
        - laravel
menu: HTTP
slug: http
---

Laravel Test: HTTP Tests



Method  | Description
------------- | -------------
`$response->assertStatus($code);`  |  Assert that the response has a given code.
`$response->assertRedirect($uri);`  |  Assert that the response is a redirect to a given URI.
`$response->assertHeader($headerName, $value = null);`  |  Assert that the given header is present on the response.
`$response->assertCookie($cookieName, $value = null);`  |  Assert that the response contains the given cookie.
`$response->assertPlainCookie($cookieName, $value = null);`  |  Assert that the response contains the given cookie (unencrypted).
`$response->assertSessionHas($key, $value = null);`  |  Assert that the session contains the given piece of data.
`$response->assertSessionHasErrors(array $keys);`  |  Assert that the session contains an error for the given field.
`$response->assertSessionMissing($key);`  |  Assert that the session does not contain the given key.
`$response->assertJson(array $data);`  |  Assert that the response contains the given JSON data.
`$response->assertJsonFragment(array $data);`  |  Assert that the response contains the given JSON fragment.
`$response->assertJsonMissing(array $data);`  |  Assert that the response does not contain the given JSON fragment.
`$response->assertExactJson(array $data);`  |  Assert that the response contains an exact match of the given JSON data.
`$response->assertJsonStructure(array $structure);`  |  Assert that the response has a given JSON structure.
`$response->assertViewHas($key, $value = null);`  |  Assert that the response view was given a piece of data.