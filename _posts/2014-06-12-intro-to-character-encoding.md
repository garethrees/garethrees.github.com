---
layout: post
title: Intro to Character Encoding
---

# {{ page.title }}

At the start of the week my knowledge of character encoding went something like:

    ASCII:   A --> 65 --> 01000001
    UNICODE: A --> U+0041 --> MAGIC --> 01000001

We all know computers work in `1`s and `0`s, but its very easy to forget all that when we're punching in letters on a keyboard and the same letter appears on the screen before you.

At some point in history ASCII became the standard in representing the characters of the English language – because those were the only ones that mattered, right?!

Each character had a number between 32 and 127 assigned (`A` got `65`, `B` got `66`, and so on), and some numbers were reserved for things like punctuation, spaces and control characters.

**Why 0-127?** First, some terminology:

- bit: a binary `0` or `1`
- byte: 8 bits (generally)

Most commonly a byte is equal to 8 bits. This means you can represent the values 0-255 in binary. I won't go in to that, but just as an example:

    DECIMAL    BINARY
    0          0000 0000
    1          0000 0001
    2          0000 0010
    3          0000 0011

By making various combinations of `1`s and `0`s we can represent the values 0-255 in just one byte. Remember, this is how things get physically written to disk.

Before 8-bit bytes there were 7-bit bytes, which gives you a range of 0-127 and hence ASCII is limited to 128 characters.

_NOTE:_ We're counting `0` (zero) as an actual value here, so 0-127 gives 128 possible numbers. Computers ehy.

When 8-bit computers came along programmers had all those spare bits to use (meaning, they got the numbers 128-255). Lots of people had this idea at the same time, each using a particular number for a potentially different character.

You'll need a little imagination here.

Lets say Bob wanted to send a greeting to Jill. Bob composes his message and adds a custom character `:)` to the end of the greeting, which is represented as `255`.

    H  E  L  L  O  :)
    72 69 76 76 79 255

When Jill receives the message, what she actually sees is "HELLO :/". Oh dear. On Jill's system the value `255` is used for the custom character `:/`. Oops.

As you can imagine, life became difficult for people using different character sets to send files and communicate with each other.

_NOTE:_ "Not 8-bit clean" is when software assumed it could use the 8th bit of each byte of text for its own purposes like in the example above.

Enter Unicode.

> Unicode provides a unique number for every character, no matter what the platform, no matter what the program, no matter what the language.

Remember, our current understanding is that a letter maps directly to a sequence of bits:

    A --> 01000001

In Unicode a letter maps to a code point – a theoretical concept. We'll get to how those are stored on disk later.

Every letter in every alphabet is assigned a code point which is written U+ followed by a hexadecimal number.

    A --> U+0041

Now we need to represent this in binary. We need an _encoding_.

There is more than one way to encode the Unicode character set. We're mostly interested in UTF-8, so we'll ignore the details of the others.

In ASCII, each character was stored in a single byte. With UTF-8 a character can take up several bytes.

- Single byte characters always have a `0` as the Most Significant Bit
- The number of significant `1` bits shows how many bytes a multibyte code point takes up
- All other bytes start with `10`

This is easier to visualise:

    'a' 0110 0001                        # 1 byte character
    'é' 1100 0011, 1010 1001             # 2 byte character
    '…' 1110 0010, 1000 0000, 1010 0110  # 3 byte character

As it happens, the Unicode code points between 0-127 are stored in a single byte with exactly the same byte sequence as ASCII, so English text stored encoded with UTF-8 will work in programs that only support ASCII.

Remember this?

    ASCII:   A --> 65 --> 01000001
    UNICODE: A --> U+0041 --> MAGIC --> 01000001

Really, the only magic part in this case is [converting from hex to decimal](http://www.binaryhexconverter.com/hex-to-decimal-converter):

    UNICODE: A --> U+0041 --> MAGIC --> 01000001
    UNICODE: A --> U+0041 --> 65 --> 01000001

It gets a little more complicated with multibyte characters.

This is the actual binary sequence we'll get if we encode U+04EC (Ӭ) with UTF-8

    # UNICODE TO BINARY
    U+04EC --> 11010011:10101100

We know `04EC` is a hexadecimal number, so we can convert that to decimal and binary.

    # HEX TO DECIMAL TO BINARY
    04EC --> 1260 --> 00000100:11101100

You can see here that the binary sequences are different, and that the hex to binary conversion doesn't follow the UTF-8 specification for multibyte characters.

For our example, its convenient to know we'll end up with a two byte character, so we can partly construct the sequence.

    # TWO BYTE CHARACTER
    11xxxxxx:10xxxxxx

We can then start to order the remaining bits (`x`) with the binary for `04EC`. We'll work from right to left.

    # 04EC
    00000100:11101100

    # FILL UP THE FIRST BYTE
    00000100:11xxxxxx
    11xxxxxx:10101100

    # USE THE SECOND BYTE FOR THE REMAINING `11`
    00000100:xxxxxxxx
    11xxxx11:10101100

    # FILL THE REMAINING BYTE
    0000xxxx:xxxxxxxx
    11010011:10101100 # OUR RESULT
    11010011:10101100 # U+04EC

Success! If we'd have been left with more non-zero values, we'd have had to have used a 3-byte character. The computer can make the assumption that the leading 4 bits of the byte are `0` if they aren't present.

You can actually encode Unicode in any encoding, but that encoding may not have a character for the code point. Lets encode two codepoints in ASCII.

    A:  U+0041 -- ASCII --> A
    Ӭ:  U+04EC -- ASCII --> �

'A' worked out fine, but ASCII doesn't have a glyph for 'Ӭ' – the cyrillic capital letter E with diaeresis – so you just get a �.

Here's the most important thing:

> **If you have a string, in memory, in a file, or in an email message, you have to know what encoding it is in or you cannot interpret it or display it to users correctly.**

Fortunately we can do this.

    # EMAIL
    Content-Type: text/plain; charset="UTF-8"
    
    # HTML
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    
    # Ruby Source
    # encoding: UTF-8

Generic text files? [Not quite as easy](http://stackoverflow.com/questions/4198804/how-to-reliably-guess-the-encoding-between-macroman-cp1252-latin1-utf-8-and).

So now I hope you know a bit more about character encoding. There are loads more details, but I hope I've covered the basics. I've mostly leaned on two main sources for getting a better understanding of this.

1. <http://www.joelonsoftware.com/articles/Unicode.html>
This is where I started and covers much of what I've regurgitated here, but with a bit more detail. I found it lacked the illustrated examples of how you convert from one thing to another.
2. <http://graysoftinc.com/character-encodings/understanding-m17n-multilingualization>
This post really helped me understand what was physically happening to the bits and bytes, but I probably wouldn't have got as far without having read Joel's article a few times to solidify the principles. It was also really useful in taking me through the practical differences of encoding between Ruby 1.8 and 1.9.

Other specific questions were answered by a bit of Googling and some Stack Overflow / Wikipedia.

I can't say I'm anywhere near an expert with encodings, but this background should be enough to at least comprehend what's going on under the hood when dealing with those funny characters.

References
----------

- <http://www.joelonsoftware.com/articles/Unicode.html>
- <http://graysoftinc.com/character-encodings/understanding-m17n-multilingualization>
- <http://en.wikipedia.org/wiki/ASCII>
- <http://en.wikipedia.org/wiki/UTF-8>
- <http://en.wikipedia.org/wiki/Unicode>
- <http://en.wikipedia.org/wiki/Bit>
- <http://en.wikipedia.org/wiki/Byte>
