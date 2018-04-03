# Slim Session Middleware

Middleware for [Slim Framework][1] that starts a session. Also provides a useful `Session` class. Forked from rka-slim-session-middleware. If in doubt you probably want that one ;)


## Usage

Add to middleware.php

    $app->add(new \Dijitaltrix\Session\Middleware([
        'name' => 'session'
    ]));


### Session

You can use `\Dijitaltrix\Session\Session` to access session variables. The main thing that this gives you is defaults and an OO interface:

    $app->get('/', function ($request, $response) {
        $session = new \Dijitaltrix\Session\Session();

        // Get session variable:
        $foo = $session->get('foo', 'some-default');
        $bar = $session->bar;

        // Set session variable:
        $session->foo = 'this';
        $session->set('bar', 'that');

        return $response;
    });
