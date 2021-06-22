**Problem Statement :**\
In the keypad, almost every digit is associated with some letters in the alphabet; this allows certain phone numbers to spell out actual words.\
For example, the phone number 8464747328 can be written as timisgreat ;\
similarly, the phone number 2686463 can be written as antoine or as ant6463.\
\
It's important to note that a phone number doesn't represent a single sequence of letters, but rather multiple combinations of letters.\
\
For instance, the digit 2 can represent three different letters (a, b, and c). A mnemonic is defined as a pattern of letters, ideas, or associations that assist in remembering something. Companies oftentimes use a mnemonic for their phone number to make it easier to remember.\
\
Given a stringified phone number of any non-zero length, write a function that returns all mnemonics for this phone number, in any order.\
\
For this problem, a valid mnemonic may only contain letters and the digits 0 and 1. In other words, if a digit is able to be represented by a letter, then it must be. Digits 0 and 1 are the only two digits that don't have letter representations on the keypad.



```python
digit_map = {
    "0": "0",
    "1": "1",
    '2': 'abc',
    '3': 'def',
    '4': 'ghi',
    '5': 'jkl',
    '6': 'mno',
    '7': 'pqrs',
    '8': 'tuv',
    '9': 'wxyz',
}
```


```python
def mnemogenHelp(number, index, output, length ,result):
    if(index == length):
        result.append("".join(output))
        return
    for i in range(len(digit_map[number[index]])):
        output.append(digit_map[number[index]][i])
        mnemogenHelp(number, index + 1, output, length,result)
        output.pop()
        if(number[index] == 0 or number[index] == 1):
            return

def mnemogen(number):
    result = []
    mnemogenHelp(number, 0, [], len(number),result)
    return result
```


```python
if 'timisgreat' in mnemogen("8464747328"):
    print('yes')
```

    yes
    


```python
mnemogen("1905")
```




    ['1w0j',
     '1w0k',
     '1w0l',
     '1x0j',
     '1x0k',
     '1x0l',
     '1y0j',
     '1y0k',
     '1y0l',
     '1z0j',
     '1z0k',
     '1z0l']




```python
mnemogen("1999")
```




    ['1www',
     '1wwx',
     '1wwy',
     '1wwz',
     '1wxw',
     '1wxx',
     '1wxy',
     '1wxz',
     '1wyw',
     '1wyx',
     '1wyy',
     '1wyz',
     '1wzw',
     '1wzx',
     '1wzy',
     '1wzz',
     '1xww',
     '1xwx',
     '1xwy',
     '1xwz',
     '1xxw',
     '1xxx',
     '1xxy',
     '1xxz',
     '1xyw',
     '1xyx',
     '1xyy',
     '1xyz',
     '1xzw',
     '1xzx',
     '1xzy',
     '1xzz',
     '1yww',
     '1ywx',
     '1ywy',
     '1ywz',
     '1yxw',
     '1yxx',
     '1yxy',
     '1yxz',
     '1yyw',
     '1yyx',
     '1yyy',
     '1yyz',
     '1yzw',
     '1yzx',
     '1yzy',
     '1yzz',
     '1zww',
     '1zwx',
     '1zwy',
     '1zwz',
     '1zxw',
     '1zxx',
     '1zxy',
     '1zxz',
     '1zyw',
     '1zyx',
     '1zyy',
     '1zyz',
     '1zzw',
     '1zzx',
     '1zzy',
     '1zzz']


