## 1. Ta có 3 cách khai báo biến:

```go
1. var <name> <type>
   => var one int; one = 1
        
2. var <name> = <value>
   => var one = 1
        
3. <name> := <value>
   => one := 1

```

**Lưu ý:** Cách khai báo 2 và 3 nên dùng ở trong một function, còn cách khai báo 1 ta thường dùng để khai báo biến global cho toàn bộ code.

Các biến được khai báo nhưng không có giá trị thì:

```go
0 for numeric types,
false for the boolean type, and
"" (the empty string) for strings.

```


## 2. Sử dụng điều kiện if/else

```go
if <condition expression> {
    // implement code
} else if <condition expression> {
    // implement code
} else {
    // implement code
}

```

## 3. If rút gọn:

```go
func pow(x, n, lim float64) float64 {
	if v := math.Pow(x, n); v < lim {
		return v
	}
	return lim
}

```

## 4. Các loại dữ liệu

```go
bool

string

int  int8  int16  int32  int64
uint uint8 uint16 uint32 uint64 uintptr

byte // alias for uint8

rune // alias for int32
     // represents a Unicode code point

float32 float64

complex64 complex128

```

## 5. Chuyển đổi loại dữ liệu

Biểu thức T(v) chuyển đổi giá trị v thành kiểu T.

```go
var i int = 42
var f float64 = float64(i)
var u uint = uint(f)

i := 42
f := float64(i)
u := uint(f)
```

Nếu như chúng ta khai báo := như thế này thì kiểu dữ liệu sẽ dựa vào value của biến đó: 

```go
i := 42           // int
f := 3.142        // float64
g := 0.867 + 0.5i // complex128

```

## 6. Khai báo hàm

```go
func <name>(param1 <type>, param2 <type>) <return type> {
    // implement code
}

// Hàm Trả về 1 giá trị:

ex: func add(x int, y int) int {
	return x + y
}

// Hàm Trả về nhiều giá trị:

ex: func swap(x, y string) (string, string) {
	return y, x
}

```

## 7. Vòng lặp for

```go
for <condition expression> {
// implement code
}

sum := 0
for i := 0; i < 10; i++ {
	sum += i
}


// Continue:
sum := 1
for ; sum < 1000; {
	sum += sum
}

// While
for sum < 1000 {
	sum += sum
}

// Nếu bạn bỏ qua điều kiện vòng lặp, nó sẽ lặp mãi mãi.
for {
}

```

## 8. Switch

```go
switch <condition expression> {
    case <condition expression>:
        // implement code
    case <condition expression>:
        // implement code
    default:
        // implement code
}

// ex:
import (
	"fmt"
	"runtime"
)

switch os := runtime.GOOS; os {
	case "darwin":
		fmt.Println("OS X.")
	case "linux":
		fmt.Println("Linux.")
	default:
		// freebsd, openbsd,
		// plan9, windows...
		fmt.Printf("%s.\n", os)
}

// Không có điều kiện:

import (
	"fmt"
	"time"
)


t := time.Now()
switch {
case t.Hour() < 12:
	fmt.Println("Good morning!")
case t.Hour() < 17:
	fmt.Println("Good afternoon.")
default:
	fmt.Println("Good evening.")
}


```


## 9. Defer

```go
defer fmt.Println("world")

fmt.Println("hello")

```

**Stacking defers:** là các hàm được gọi nhưng chưa được thực hiện và bị đẩy lên stack. Khi hàm chính hoàn thành, các hàm chưa thực hiện nó sẽ được chạy theo thứ tự LIFO ( Last-in-First-out ).

```go
defer fmt.Println("world")
defer fmt.Println("hello")
```

## **Tổng kết:**

- cách khai báo biến
- câu lệnh if/else
- các kiểu dữ liệu
- khai báo hàm.
- Vòng lặp For
- Switch
- Defer, Stacking Defer
