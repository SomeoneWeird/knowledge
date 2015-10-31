
# NAN

## Conversions

### Nan::MaybeLocal<T> -> Nan::Local<T>

```c++
Nan::MaybeLocal<T> maybeLocal = ...;

Nan::Local<T> local;

if(maybeLocal.ToLocal(&local) == false) {
  Nan::ThrowError("Error converting");
}
```

### Nan::Maybe<T> -> T

```c++
Nan::Maybe<T> maybe = ...;

if(maybe.IsNothing() == true) {
  Nan::ThrowError("Error converting");
}

<T> value = maybe.FromJust();
```
