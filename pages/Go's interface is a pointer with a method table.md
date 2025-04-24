---
title: "Go's interface is a pointer with a method table"
---

- [[Go Interface]] is [[pointer]] with [[method table]].
- The word [[interface]] confuses people when they think of [[Java Interfaces]].

go

```
// emptyInterface is the header for an interface{} value.
type emptyInterface struct {
	typ  *rtype
	word unsafe.Pointer
}

// nonEmptyInterface is the header for an interface value with methods.
type nonEmptyInterface struct {
	// see ../runtime/iface.go:/Itab
	itab *struct {
		ityp *rtype // static interface type
		typ  *rtype // dynamic concrete type
		hash uint32 // copy of typ.hash
		_    [4]byte
		fun  [100000]unsafe.Pointer // method table
	}
	word unsafe.Pointer
}
```

[https://github.com/golang/go/blob/7e987b7/src/reflect/value.go#L180-L197](https://github.com/golang/go/blob/7e987b7/src/reflect/value.go#L180-L197)

I thought I couldn't find it in my search tied to the C language, but it was in *.go.


---
This page is auto-translated from [/nishio/Goのインターフェイスはポインタにメソッドテーブルがついたもの](https://scrapbox.io/nishio/Goのインターフェイスはポインタにメソッドテーブルがついたもの) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.