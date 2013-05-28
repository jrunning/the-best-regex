U.S. postal code (ZIP code)
===========================

A United States postal code, or [ZIP code], is five arabic numbers optionally
followed by a hyphen and four numbers.

    captures:
      1: zip_plus4 - The complete ZIP+4 postal code
      2: zip       - The five-digit ZIP code
      3: plus4     - The last four digits

    implementations:
      named_capture:
        - |-
          (?<zip_plus4>           # The complete ZIP+4 postal code
            (?<zip>[0-9]{5})      # The five-digit ZIP code
            ((?:-)                # The hyphen (don't capture)...
              (?<plus4>[0-9]{4})  # and the last four digits
            )?                    # ...are optional
          )

        - (?<zip_plus4>(?<zip>[0-9]{5})((?:-)(?<plus4>[0-9]{4}))?)

[ZIP code]: http://en.wikipedia.org/wiki/ZIP_code
