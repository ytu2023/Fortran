## 第二次课

## 第一个程序
> 这是文件读取，在文件的当前目录下，PPT19页
> 
```
program tt
REAL A,B,C
OPEN( 1, FILE = 'DATA1' )
OPEN( 2, FILE = 'DATA2' )
READ(1, 5) A, B, C
WRITE(2,5) A, B, C
5 FORMAT(1X,3F12.5)
END

```


```
PROGRAM Final_Mark
! Final mark for course based on class record and exams
IMPLICIT NONE
REAL CRM ! Class record mark
REAL ExmAvg ! average of two exam papers
REAL Final ! final mark
REAL P1 ! mark for first paper
REAL P2 ! mark for second paper
INTEGER Stu ! student counter
! file wire in
CHARACTER (Len = 15) Name ! Name
OPEN( 1, FILE = 'MARKS.txt' )
write(*,*) ' CRM Exam Avg Final Mark'
write(*,*)
DO Stu = 1, 3
    READ( 1, * ) CRM, P1, P2 READ( 1, * ) Name, CRM, P1, P2
    ExmAvg = (P1 + P2) / 2.0
    IF (ExmAvg > CRM) THEN
    Final = ExmAvg
    ELSE
    Final = (P1 + P2 + CRM) / 3.0
    END IF
    IF (Final >= 50) THEN
    write(*,*) CRM, ExmAvg, Final, 'PASS'
    ELSE
    write(*,*) CRM, ExmAvg, Final, 'FAIL'
END IF
END DO
END

```
## 运行结果
这个需要文件操作，我没运行








