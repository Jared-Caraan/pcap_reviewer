## Internal string representation

### Basic character encoding
Deep down, computers store characters as numbers. Every character has a unique number, and every unique number corresponds to a unique character. There are some characters that may seem obvious, such as small letter "a" or capital letter "a", but there are also some other characters which are less obvious. There is a dedicated number for a space that we usually use between words in a sentence and another number for a character that indicates the end of a line something like an "Enter" character. This representation of characters as numbers is often called **character encoding**.

<img width="841" height="447" alt="image" src="https://github.com/user-attachments/assets/feece213-aae9-4a1f-be62-575a50442a0e" /><br>

In practice, there are some standard encodings that almost all computers in operating systems have in common. One of the most widely used encodings in the world is called ASCII, which is short for American Standard Code for Information Interchange. This code provides space for 256 different characters, of which the first half, the first 128 characters are the most significant ones.

<img width="870" height="455" alt="image" src="https://github.com/user-attachments/assets/8502e5b4-2ac6-42c0-b057-099237ba93a5" /><br>

Take a look at the ASCII encoding table. Now, for instance, you can see that a small letter `a` has a code of **97**. A big letter `A` has a different number, **65**. A plus sign is assigned to the number **43**, and a space character can be found under **32**. These numbers representing concrete characters are called **code points**. And of course, internally, deep down in your computer, those integer numbers are translated into bits - long sequences of zeros and ones.

<img width="716" height="485" alt="image" src="https://github.com/user-attachments/assets/a874e7fe-0c9a-4c70-8341-64c3bf5b67b2" /><br>

ASCII encoding allows you to represent 256 characters. 256 character possibilities translates to eight bits or one byte.

<img width="665" height="422" alt="image" src="https://github.com/user-attachments/assets/c5d94d25-c34e-48f5-ac0a-b59d7bb79594" /><br>
<hr>

### Foreign characters
The ASCII table looks very sweet, but there is a problem. It's only covers the basic Latin alphabet that we mostly use in English. How about special characters that you will find in other languages? In this case, we use the concept of a **code page**. A code page is a standard for using the remaining 128 code points for ASCII to store specific national characters. All of the code pages share the first 128 code points that you have seen already. You will find different code pages for languages from Western Europe, Eastern Europe, Cyrillic or Greek. This means that the same code point or in other words, the same number in the ASCII table could represent different characters depending on the code page.

For instance, the ISO/IEC 8859-2 code page for languages such as German, Polish or Czech. In these languages, in this code page, the code point 223 means _sharp s_ `ß`, the character used in German.
<img width="862" height="472" alt="image" src="https://github.com/user-attachments/assets/cf972ddf-789c-49cb-af75-6848ba3ad50e" /><br>

But the same codes point to 223 in ISO/IEC 8859-5 for Cyrillic is the letter pe `п` in this particular alphabet.

<img width="850" height="478" alt="image" src="https://github.com/user-attachments/assets/43e0495c-c6fc-421b-8116-e7d3894fdb8c" /><br>

All of this means that if you want to know the character behind a given number, behind a given code point, and that code point is higher than 128, you need to know which code page we are talking about.
<hr>

### Unicode

The concept of finding a solution to the problem with multiple alphabets for multiple languages is known as _i18n_, it is short for **internationalization**. At some point, computer scientists decided it was time to find a better, more universal encoding. This universal encoding is called **Unicode**. Unicode doesn't use code pages, so there is no choosing between specific encoding for specific languages. Each character has its own unique number, and Unicode can store more than a million different code points. The first 128 code points in Unicode are identical with ASCII, and the next 128 code points are identical with the code page designed for Western languages.

<img width="827" height="473" alt="image" src="https://github.com/user-attachments/assets/b821beff-2aaa-4e3c-95b9-316d7b3a053a" /><br>

But Unicode is actually just a standard. It doesn't explain how to code or store all the characters in the memory of your computer. Unicode only lists all the available characters, and each character can be placed in a plane. A **plane** is a group of similar characters. There are 17 planes in total.

For instance, the first plane is the so called **Basic Multilingual Plane**. Plane two in turn is the **Supplementary Ideographic Plane** for languages such as Japanese or Korean.

There is more than one technique to actually implement Unicode in specific computers. One of the most widely known standards is UCS-4. **UCS** is short for **Universal Character Set**. In UCS-4 each character uses 32 bits or four bytes to store a character. The problem with UCS-4, however, is that it takes a lot of space. You need as many as 32 bits to keep a single character. If you compare that to eight bits in ASCII, you will quickly see that your files grow in size four times.

<img width="752" height="341" alt="image" src="https://github.com/user-attachments/assets/4096f957-29eb-43db-9b4a-7777a1bb965e" /><br>

Fortunately, there are other forms of encoding Unicode. One of them is called UTF-8. The good thing about UTF-8 is that it only uses as many bits for each character as are really needed. All standard ASCII characters occupies exactly eight bits, just like in the ASCII format. Non-Latin characters from other languages like Polish or Spanish occupy 16 bits. And the characters used in China, Japan and Korea occupy 24 bits. 

<img width="750" height="430" alt="image" src="https://github.com/user-attachments/assets/d527c45f-8f45-4416-9692-154c5fb9aee1" /><br>

Python fully supports UTF eight. You can use UTF eight characters to name your variables. In practice, this means that your variables could be written in English, Spanish, or even Japanese characters. And Python will do just fine. You can also use all UTF-8 characters during input and output. If you ask a user to provide their name using the input function and they provide something in Japanese characters, Python will take care of that without any problems.
