# KEG URLs Have No Schema

KEG is transport agnostic. Therefore, any specification of a KEG URL
most not require a specific schema, only the domain. It is up to the
user/client adding a KEG site to their follows to specify (potential
after initial discovery) what protocol is preferred, but this
information is never stored with the follows list in /KEG since every
user may have a different protocol preference.

    #keg #spec #urls
