# Kotlin Coroutines Notes

## 📌 Key Concepts

### What is a Coroutine?
A coroutine is a lightweight thread for asynchronous programming.

## 🚀 Basic Syntax

```kotlin
// Launch a coroutine
CoroutineScope(Dispatchers.Main).launch {
    // Do work in background
    val result = withContext(Dispatchers.IO) {
        fetchData()
    }
    // Update UI on main thread
    textView.text = result
}
```

## 📦 Common Dispatchers

| Dispatcher | Use Case |
|------------|----------|
| `Dispatchers.Main` | UI operations |
| `Dispatchers.IO` | Network, disk I/O |
| `Dispatchers.Default` | CPU-intensive work |

## 🔄 Flow

```kotlin
fun fetchData(): Flow<Data> = flow {
    while (true) {
        emit(api.getData())
        delay(5000) // Poll every 5 seconds
    }
}

// Collect in ViewModel
viewModelScope.launch {
    fetchData().collect { data ->
        _uiState.value = data
    }
}
```

## ⚠️ Exception Handling

```kotlin
viewModelScope.launch {
    try {
        val result = withContext(Dispatchers.IO) {
            riskyOperation()
        }
    } catch (e: Exception) {
        Log.e("Error", e.message)
    }
}
```

## 📚 Resources

- [Official Docs](https://kotlinlang.org/docs/coroutines-guide.html)
- [Android Codelab](https://developer.android.com/courses/android-kotlin-fundamentals/codelab)

---
*Notes by Rushikesh*
