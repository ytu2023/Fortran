## 选择与分支结构
> 这个程序将不断读取输入，直到遇到文件结束。它会根据给定的最终成绩，输出相应的等级，并计算每个等级的学生人数。最后，程序将输出每个等级的人数总结。

```
PROGRAM GradeReport
    IMPLICIT NONE

    CHARACTER(LEN=20) :: Name
    REAL :: CRM, ExmAvg, Final
    INTEGER :: Firsts, UpSeconds, LowSeconds, Thirds, Fails

    Firsts = 0
    UpSeconds = 0
    LowSeconds = 0
    Thirds = 0
    Fails = 0

    ! Read input until end of file
    DO WHILE ( .TRUE. )
        READ(*,*,END=10) Name, CRM, ExmAvg, Final
        IF (Final >= 75) THEN
            PRINT*, Name, CRM, ExmAvg, Final, '1'
            Firsts = Firsts + 1
        ELSE IF (Final >= 70) THEN
            PRINT*, Name, CRM, ExmAvg, Final, '2+'
            UpSeconds = UpSeconds + 1
        ELSE IF (Final >= 60) THEN
            PRINT*, Name, CRM, ExmAvg, Final, '2--'
            LowSeconds = LowSeconds + 1
        ELSE IF (Final >= 50) THEN
            PRINT*, Name, CRM, ExmAvg, Final, '3'
            Thirds = Thirds + 1
        ELSE
            PRINT*, Name, CRM, ExmAvg, Final, 'F'
            Fails = Fails + 1
        END IF
    END DO

    ! Output summary
    PRINT*, 'Number of Firsts: ', Firsts
    PRINT*, 'Number of Upper Seconds: ', UpSeconds
    PRINT*, 'Number of Lower Seconds: ', LowSeconds
    PRINT*, 'Number of Thirds: ', Thirds
    PRINT*, 'Number of Fails: ', Fails

10  CONTINUE

END PROGRAM GradeReport

```

## 嵌套选择

···
Disc = B * B
4 * A * C
Outer
: IF (A /= 0) THEN
Inner
: IF (Disc < 0) THEN
PRINT*, 'Complex roots'
ELSE Inner
X1 = (
B + SQRT( Disc )) / (2 * A)
X2 = (
B SQRT( Disc )) / (2 * A)
END IF Inner
END IF Outer
```

##循环嵌套Do

> 计算利率

```
PROGRAM LoanPayments
    IMPLICIT NONE

    INTEGER :: I ! counter
    INTEGER :: N = 12 ! number of payments per year
    INTEGER :: K ! repayment period (yrs)
    INTEGER :: TRIPS ! iteration count
    REAL :: A = 1000.0 ! principal
    REAL :: P ! payment
    REAL :: R ! interest rate
    REAL :: R0, R1, RINC ! lowest, highest interest and increment

    write(*,*) "请输入：最低利率（R0）、最高利率（R1）和增量（RINC）"
    READ(*,*) R0, R1, RINC

    TRIPS = INT( (R1 - R0) / RINC + RINC/2 ) + 1
    R = R0

    PRINT*, "Rate  15 yrs   20 yrs   25 yrs"
    PRINT*, "--------------------------------"

    DO I = 1, TRIPS
        WRITE( *, '(F5.2, "%")', ADVANCE = 'NO' ) 100 * R
        DO K = 15, 25, 5
            P = R/N * A*(1 + R/N)**(N*K) / ((1 + R/N)**(N*K) - 1)
            WRITE( *, '(F10.2)', ADVANCE = 'NO' ) P
        END DO
        PRINT* ! get a new line
        R = R + RINC
    END DO

END PROGRAM LoanPayments

```


##
>

```

```


##
>

```

```


##
>

```

```

##
>

```

```



##
>

```

```


##
>

```

```


##
>

```

```


##
>

```

```


##
>

```

```


##
>

```

```



