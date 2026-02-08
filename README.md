# Python BBC BASIC II Tokenizer / Detokenizer

# Two standalone pure python files to tokenize and detokenize BBC BASIC II files

## bbc_basic_detokenizer.py

    Converts a tokenized BBC BASIC II file into detokenized ASCII BASIC source code.

    By default, unprintable characters are converted to "\x07" style strings to give a pure ASCII result.
    To override this behaviour, add the "--no_escape" argument. In this case, non-printable characters will be output as raw binary.

    Usage: python3 bbc_basic_detokenizer.py <input_tokenized_file> <output_text_file> {--no_escape}

## bbc_basic_tokenizer.py

    Converts detokenized ASCII BASIC source code into tokenized BBC BASIC II format.

    By default, if the input contains an escaped character string such as "\x07" this is converted back to the single character equivalent.
    To disable this behaviour add the "--no_escape" argument.

    Usage: python3 bbc_basic_tokenizer.py <input_text_file> <output_tokenized_file> {--no_escape}

TobyLobster, Feb 2026
