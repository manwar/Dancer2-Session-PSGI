# NAME

Dancer2::Session::PSGI - Dancer2 session storage via Plack::Middleware::Session

# VERSION

version 0.010

# SYNOPSIS

    use Dancer2;

    setting( session => 'PSGI' );

    get '/' => sub {
        my $count = session("counter");
        session "counter" => ++$count;
        return "This is my ${count}th dance";
    };

# DESCRIPTION

This module implements implements a session factory for Dancer2 that uses
[Plack::Middleware::Session](https://metacpan.org/pod/Plack::Middleware::Session) for session management.

# CONFIGURATION

The setting **session** should be set to `PSGI` in order to use this session
engine in a Dancer2 application.

The default cookie name is `plack_session`. Refer to
["Session\_engine" in Dancer2::Config](https://metacpan.org/pod/Dancer2::Config#Session_engine) if you need to modify this.

# ACKNOWLEDGEMENTS

The methods required by [Dancer2::Core::Role::SessionFactory](https://metacpan.org/pod/Dancer2::Core::Role::SessionFactory) were
heavily based on [Dancer2::Session::Cookie](https://metacpan.org/pod/Dancer2::Session::Cookie) by David Golden.

# AUTHOR

Russell Jenkins <russellj@cpan.org>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2014 by Russell Jenkins.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
