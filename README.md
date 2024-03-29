# Argument-Robot-Framework
เทคนิคการใช้ Argument ใน Robot Framework

Noted: Arguments แบ่งเป็น 4 แบบ positonal, named, vararg, kwargs

-positional ตามตําแหน่ง

-named กําหนดชื่อ argument ไว้เลย ซึ่งเราสามารถกําหนดค่า default ของมันไว้ได้ด้วย ถ้าในกรณีข้างบนก็คือ arg= 

-vararg คือ *args ใช้เมื่อเราไม่รู้จํานวนที่สิ้นสุดของ argument นั้น

-kwarg คือแบบเดียวกันกบั vararg เพียงแต่จะมาในรูปของ dictionary และไม่สิ้นสุด

# Tags-Robot-Framework
ส่วนวิธีรัน Robot ที่มี Tag ทำได้ดังนี้

    $ robot -i regression test.robot

    -i หมายถึง include ซึ่งผลลัพธ์ที่ได้ robot จะรันแค่ test case ที่มี tag regression

     $ robot -e regression test.robot

    -e หมายถึง exclude ซึ่งผลลัพธ์ที่ได้ robot จะไม่รัน test case ที่มี tag regression

Today we will learn:
------------------------------
1. How to run one specific Test from cmd
2. How to run few selected Tests from cmd
3. How to run tests with TAGS from cmd
4. How to run all Tests in a Suite from cmd
5. How to send RESULTS to a specific folder

Step 1 : Open cmd and goto the location of project 

Step 2 : Run single test

             robot -t TestName SuiteFile

Step 3 : Run multiple tests

             robot -t Test1 -t Test2 SuiteFile

Step 4 : Run Tests with TAGS

             Include TAGS
             robot --include tagName SuiteFile
             robot -i tagName SuiteFile
             robot -i tagName -i tagName SuiteFile
             robot -i S* SuiteFile

             Exclude TAGS
             robot --exclude tagName SuiteFile
             robot -e tagName SuiteFile
             robot -e tagName -e tagName SuiteFile
             robot -e S* SuiteFile

Step 5 : Run all tests in a test suite

             robot suiteFile

Step 6 : Send results to a folder

             robot -t Test5 -d Results TestSuite1.txt
            


Useful TIPS
Using regular expressions

how to make tags critical / non-critical
e.g.

      robot -i S* --critical Smoke TestSuite1.txt
      robot -i S* -c Smoke TestSuite1.txt
      robot -i S* --noncritical Smoke TestSuite1.txt
      robot -i S* -n Smoke TestSuite1.txt
