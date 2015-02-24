#Timer

A simple but powerful C++ code performance measurement library which just contains a single header file.

Simple example within the timer.h file

```
inline void* timer_malloc(size_t size) {
  TIMER_FLOPS("timer_malloc", size);
  void* p = malloc(size);
  memset(p, 0, size);
  return p;
}

inline void timer_free(void* ptr) {
  TIMER("timer_free");
  free(ptr);
}

#define malloc(x) timer_malloc(x)

#define free(x) timer_free(x)
```
