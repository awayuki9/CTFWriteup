nohtyp1 - easy [70 points]

We love snakes.

Hints:
$ cat flag | md5sum 
5a76c600c2ca0f179b643a4fcd4bc7ac

-------------------------------------------------------------------

start with nohtyp1.py_fix

1. rename to nohtyp1.py

2. editcode format for easy to understand
--first edit--
```python
____=input;
__________________=print;
___________=____();
_________=map;
__________=ord;
_______________=zip;
____________________________=list;
___=21;
_____=lambda ______,_______:______+(_______^___);______________={not not not ___ and not not ___:lambda:__________________('\x41\x6c\x6d\x6f\x73\x74\x21\x21'),not not ___ and not not ___:lambda:__________________('\x43\x6f\x72\x72\x65\x63\x74\x21')};
______________[[_____(*________) for ________ in _______________(____________________________(_________(__________,___________)),____________________________(_________(__________,___________))[::-1])][::-1]==[160,155,208,160,190,215,237,134,210,126,212,222,224,238,128,240,164,213,183,192,162,178,163,162] and 'mo4r' in ___________ and '34C3_' in ___________ and ___________.split('_')[3] == 'tzzzz']()
```
--second edit--
```python
input=input;#4
print=print;#18
Inn=input();#11
map=map;#9
ord=ord;#10
zip=zip;#15
list=list;#28
temp3=21;#3

Lambda=lambda t1,t2:t1+(t2^temp3); #5
cal14={not temp3 and temp3:lambda:print("STOP!!"),temp3 and temp3:lambda:print('Correct!')}; #14
cal14[[Lambda(*________) for ________ in zip(list(map(ord,Inn)),list(map(ord,Inn))[::-1])][::-1]==[160,155,208,160,190,215,237,134,210,126,212,222,224,238,128,240,164,213,183,192,162,178,163,162] and 'mo4r' in Inn and '34C3_' in Inn and Inn.split('_')[3] == 'tzzzz' ]()
```
3. understand code

at first code want your string input and stroage input as list of [ord(input(i)),ord(input(n-i))] when 'i' is position of char from first to last.
stroage data [t1,t2] use Lambda function to calculate with t1+(t2^21)

[::-1]==[160,155,208,160,190,215,237,134,210,126,212,222,224,238,128,240,164,213,183,192,162,178,163,162] is a reverse string answer (24 char)
and we know somepart of answer : '34C3_'at fist //'mo4r' //'tzzzz' at last

4. test some piece with code
```python
#[160,155,208,160,190,215,237,134,210,126,212,222,224,238,128,240,164,213,183,192,162,178,163,162]
#  ^                                                                                           ^
Lambda=lambda t1,t2:t1+(t2^21)
for i in range(1,127):
    for j in range(1,127):
        t1 = Lambda(i,j)
        t2 = Lambda(j,i)
        if t1 == 162 and t2 == 160 and i >= 48 and i <= 122 and j >= 48 and j <= 122:
            print(str(i)+" "+str(j))
```
```
--output--            
3 z
; r
? v
C J
G N
K B
O F
S Z
W ^
[ R
_ V
s :
w >
------
```
'3' in first '34C3_' and 'z' in last 'tzzzz' is Correct!
that you need to compare 2 char in some part of answer

5. flag : 34C3_mo4r_schn4kes_tzzzz


