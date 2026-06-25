# Jetpack Compose Notes

## 📌 Key Concepts

### What is Jetpack Compose?
A modern toolkit for building Android UI declaratively.

## 🚀 Basic Components

```kotlin
@Composable
fun Greeting(name: String) {
    Text(
        text = "Hello, $name!",
        style = MaterialTheme.typography.headlineMedium
    )
}
```

## 📦 Common Components

| Component | Description |
|-----------|-------------|
| `Text` | Display text |
| `Button` | Clickable button |
| `Image` | Display images |
| `TextField` | Input field |
| `Card` | Material card |
| `Column` | Vertical layout |
| `Row` | Horizontal layout |

## 🎨 Styling

```kotlin
Text(
    text = "Styled Text",
    color = Color.Blue,
    fontSize = 24.sp,
    fontWeight = FontWeight.Bold,
    modifier = Modifier.padding(16.dp)
)
```

## 🔄 State Management

```kotlin
@Composable
fun Counter() {
    var count by remember { mutableStateOf(0) }
    
    Button(onClick = { count++ }) {
        Text("Count: $count")
    }
}
```

## 📚 Resources

- [Official Docs](https://developer.android.com/jetpack/compose)
- [Cheat Sheet](https://compose-cheatsheet.com)

---
*Notes by Rushikesh*
