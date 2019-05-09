# Hacking vs. Engineering

Recently studying both Rust and Ruby, I've found myself questioning the roles
of each in the universe of software development. My theory so far is that there
is a continuum between two extreme modes of software development. On the one
extreme is what I will label as "hacking", an approach of writing functional,
effective software extremely fast without much, if any, regard for the
longevity of the software. On the other extreme is what I will label as
"Engineering", an approach to writing software that favours correctness,
reliability and longevity of the software at the expense of development speed.

 Hacking <---------------------------------> Engineering

With this model available, we can easily conclude that there are varying
circumstances where any given tool and development style may be more
appropriate. Perhaps this model can also be used to help identify when each
tool will be most appropriate for a given system. Finally, I hope this model
could inform when to transition from one mode to another; for example, when a
development team has proven product viability with a more "hacky" solution and
now the team needs to decide when to transition the system, as a whole or in
part, to be more methodically engineered.

## Hacking

Here are some features of Ruby that make it an excellent example of a
hacking-oriented language.

- Numerous shorthands which act as force multipliers in productivity as an
engineer gains experience.
- Simplicity of concepts. Everything is an object. Anything can be bent to the
whims of the engineer.
- Concise, readable style. The syntax lends itself to allowing maximum
productivity with few keystrokes, likewise, it is relatively easy to read.
- Ability to alter module behaviour at runtime (monkey patching).
- Opaque memory management that just works.

## Engineering

Here are some features of Rust that make it an excellent example of an
engineering-oriented language.

- Extensive compile-time guarantees.
- Explicit memory management including for shared resources.
- Minimal memory, CPU overhead.

## Application

Virtually any software system today will feature a tree of dependent software -
from tens to hundreds of layers deep. In a modern web application, these might
progress from the client app running in a user's browser to the web front end
running the API to a backend service to a database engine to the file system
implementation to the hardware controllers on a disk drive. As we progress
through each of these layers, from the user-facing application onward, we
observe a continuing decrease in uncertainty about how the software should
behave and increasing need for reliability and accuracy. For example, it would
be common for a client app to be updated daily, with new features being added
and evolved constantly; however, it would be extremely uncommon for widely-used
hardware drivers to be evolved on even an annual basis aside from the odd
security on bug patch. Likewise, a web client which fails one request out of
every one thousand would be, at most, annoying. A filesystem implementation
failing one out of one thousand requests, however, would be unusable.

As we progress through these layers, the need for rapid software development
decreases and the need for reliable engineering increases. Thus, the
appropriate tooling evolves as we move through the stack.

## Are you writing one app or 20?

A wannabe entrepreneur in Silicon Valley may easily write a product a year (or
five) in ongoing attempts to validate ideas. This is the domain of the hacker.

In contrast, consider a company which has established at least a minimal
product-market fit and is now in the process of iterating on the one product.
This product will, most likely, live in one form or another for the lifetime of
the company. This is the domain of the engineer.

## ORMs

Eli Benderski wrote
[a good blog post](https://eli.thegreenplace.net/2019/to-orm-or-not-to-orm/) on
the benefits and drawbacks of ORMs by exploring a specific example, gorm. I
immediately realised that ORMs fit within the domain of the hacker. They reduce
boilerplate at the expense of fine-grained control. An ORM requires an up-front
investment in learning the framework for the long-term benefit of reducing the
amount of code necessary for each database interaction written. However, when
working on a long-lived system (the domain of the Engineer), very little time is
spent writing database interactions. The cost of handrolled SQL is minimal and
the cost of learning an ORM framework, and the lack of control over queries,
becomes significant.
