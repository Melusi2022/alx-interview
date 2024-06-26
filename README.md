UTF-8: 

UTF-8 has truly been the dominant character encoding for the World Wide Web since 2009, and as of June 2017 accounts for 89.4% of all Web pages. UTF-8 encodes each of the 1,112,064 valid code points in Unicode using one to four 8-bit bytes. Code points with lower numerical values, which tend to occur more frequently, are encoded using fewer bytes. The first 128 characters of Unicode, which correspond one-to-one with ASCII, are encoded using a single octet with the same binary value as ASCII, so that valid ASCII text is valid UTF-8-encoded Unicode as well. So how many bytes give access to what characters in these encodings?

UTF-8:

1 byte: Standard ASCII 2 bytes: Arabic, Hebrew, most European scripts (most notably excluding Georgian) 3 bytes: BMP 4 bytes: All Unicode characters

UTF-16:

2 bytes: BMP 4 bytes: All Unicode characters

So I did make a mention about BMP. What is it exactly?

Basic Multilingual Plane (BMP) contains characters for almost all modern languages, and a large number of symbols. A primary objective for the BMP is to support the unification of prior character sets as well as characters for writing. UTF-8, UTF-16 and UTF-32 are encodings that apply the Unicode character table. But they each have a slightly different way on how to encode them. UTF-8 will only use 1 byte when encoding an ASCII character, giving the same output as any other ASCII encoding. But for other characters, it will use the first bit to indicate that a 2nd byte will follow. UTF-16 uses 16-bit by default, but that only gives you 65k possible characters, which is nowhere near enough for the full Unicode set. So some characters use pairs of 16-bit values. UTF-32 is opposite, it uses the most memory (each character is a fixed 4 bytes wide), which makes it quite bloated but now in this scenario every character has this precise length, so string manipulation becomes far simpler. You can compute the number of characters in a string simply from the length in bytes of the string. You can’t do that with UTF-8.This is how it eases to accommodate the entire character set for different languages and help people spread their applications or information to the world just coding/writing in their language rest all is taken care by the Decoder. As this being just the beginning into the world of Character Encoding. I hope this helps you understand Character encoding at a higher level.
