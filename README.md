# Python BBC BASIC II Tokenizer / Detokenizer

Two standalone pure python files to tokenize and detokenize BBC BASIC II files.

## bbc_basic_detokenizer.py

Converts a tokenized BBC BASIC II file into a pure ASCII BASIC source code.

Detokenized BASIC files are stored as pure 7-bit ASCII text as they would be typed at the BASIC prompt, with the following exceptions:


| Markup    | Meaning |
| --------- | ------- |
| `\\x87`    | Inserts a non-printable byte (e.g. for MODE 7 graphics in a `PRINT` statement) |
| `\\{IF}`   | Inserts the keyword token byte for `IF`, even where it would not normally be tokenized by BASIC |
| `\\{"IF"}` | Inserts the ASCII `I` and `F`, even where it would normally be tokenized by BASIC |
| `\\{54321}` | Tokenizes a line number even if it would not normally be tokenized by BASIC |
| `\\\\`      | Inserts a single backslash |

If the file ends with a line `\\xCC` this denotes the terminator byte, which by default is FF, but can be any top bit set character.

The pound '£' symbol is not ASCII, so to keep things pure ASCII we use the back-tick character.

    Usage: python3 bbc_basic_detokenizer.py <input_tokenized_file> <output_text_file>

## bbc_basic_tokenizer.py

Converts a detokenized pure ASCII BASIC source code into tokenized BBC BASIC II format.

    Usage: python3 bbc_basic_tokenizer.py <input_text_file> <output_tokenized_file>

TobyLobster, Feb-Mar 2026.  