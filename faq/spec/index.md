---
title: HTTP FAQs for Specification Writers
description: Frequently Asked Questions from people who are specifying HTTP extensions like new header fields
---

*This page lists Frequently Asked Questions from people who are specifying HTTP extensions like new header fields.*


<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [How do I reference the HTTP specification?](#how-do-i-reference-the-http-specification)
- [How do I create a new HTTP header?](#how-do-i-create-a-new-http-header)
- [How do I create a new HTTP method?](#how-do-i-create-a-new-http-method)
- [How do I create a new HTTP Status Code?](#how-do-i-create-a-new-http-status-code)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## How do I reference the HTTP specification?

Most specifications can get away with referencing
[RFC7230](http://httpwg.github.io/specs/rfc7230.html), the "core" of HTTP. If
you need to reference a specific method, status code or payload consideration,
you'll also probably need to reference
[RFC7231](http://httpwg.github.io/specs/rfc7231.html).

This includes when you're specifying that you're extending HTTP, using HTTP, or
otherwise talking about HTTP in the abstract; these documents define HTTP
overall, and are backwards-compatible with HTTP/1.0 and forwards-compatible
with HTTP/2 (and beyond). 

There isn't any need to reference the HTTP/2 specification directly, unless
you're doing something specific to it (e.g., a new error code, extension frame
type or the like).

If you talk about conditional requests, range requests, caching or
authentication, you might consider referencing RFCs
[7232](http://httpwg.github.io/specs/rfc7232.html),
[7233](http://httpwg.github.io/specs/rfc7233.html),
[7234](http://httpwg.github.io/specs/rfc7234.html) or
[7235](http://httpwg.github.io/specs/rfc7235.html) (respectively.)

RFC1945, RFC2068 and RFC2616 should not be referenced, unless you specifically need to talk about those documents in particular. 

## How do I create a new HTTP header?

The best place to start is [Considerations for New Header
Fields](http://httpwg.github.io/specs/rfc7231.html#considerations.for.new.header
.fields) in RFC7230; it covers most common questions, and has a checklist for
header authors.

If you have questions, the best place to ask is the [HTTP Working Group mailing
list](http://lists.w3.org/Archives/Public/ietf-http-wg/).

New HTTP headers ought to be registered, to assure that you don't collide with
other headers, and so that people can more easily find out more about your
header when they see it. [RFC3864](http://tools.ietf.org/html/rfc3864) explains
how.

The [Permanent Message Header
Registry](http://www.iana.org/assignments/message-headers/message-headers.xhtml#
perm-headers) is for standard headers; if you just want to avoid collisions,
you can get your header registered much more easily in the [Provisional Message
Header
Registry](http://www.iana.org/assignments/message-headers/message-headers.xhtml#
prov-headers).


## How do I create a new HTTP method?

New HTTP methods are relatively uncommon, because a lot of the value in HTTP is
having a constrained, generic set of methods.

[Considerations for New
Methods](http://httpwg.github.io/specs/rfc7231.html#considerations.for.new.metho
ds) in RFC7231 is a good place to start for those thinking about creating a
method.

If your idea for a new method seems like a good idea after reading that, the
best thing to do is to bring it up on the [HTTP Working Group mailing
list](http://lists.w3.org/Archives/Public/ietf-http-wg/).


## How do I create a new HTTP Status Code?

Like methods, new HTTP status codes are fairly rare -- not least because there
are only a limited number of unused codes available.

[Considerations for New Status
Codes](http://httpwg.github.io/specs/rfc7231.html#considerations.for.new.status.
codes) in RFC7231 is a good place to start for those thinking about creating a
status code.

If you have an idea for a new status code, the best thing to do is to bring it
up on the [HTTP Working Group mailing
list](http://lists.w3.org/Archives/Public/ietf-http-wg/), where people can
discuss it and point you in the right direction if this isn't the best solution
for your problem.
