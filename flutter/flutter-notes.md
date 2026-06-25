# Flutter Notes

## 📌 Key Concepts

### What is Flutter?
Flutter is Google's UI toolkit for building beautiful, natively compiled applications for mobile, web, and desktop from a single codebase.

## 🚀 Creating a Flutter App

```bash
flutter create my_app
cd my_app
flutter run
```

## 📦 Widgets

### Stateless vs Stateful

```dart
// StatelessWidget - immutable
class MyWidget extends StatelessWidget {
  const MyWidget({super.key});
  
  @override
  Widget build(BuildContext context) {
    return const Text('Hello');
  }
}

// StatefulWidget - mutable
class CounterWidget extends StatefulWidget {
  const CounterWidget({super.key});
  
  @override
  State<CounterWidget> createState() => _CounterWidgetState();
}

class _CounterWidgetState extends State<CounterWidget> {
  int _count = 0;
  
  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        Text('$_count'),
        ElevatedButton(
          onPressed: () => setState(() => _count++),
          child: const Text('Increment'),
        ),
      ],
    );
  }
}
```

## 🗺️ Navigation

```dart
// Named route
Navigator.pushNamed(context, '/details', arguments: item);

// MaterialPageRoute
Navigator.push(
  context,
  MaterialPageRoute(builder: (context) => const DetailsPage()),
);
```

## 🔄 State Management

### Provider
```dart
class CounterProvider extends ChangeNotifier {
  int _count = 0;
  int get count => _count;
  
  void increment() {
    _count++;
    notifyListeners();
  }
}
```

### Riverpod
```dart
final counterProvider = StateNotifierProvider<CounterNotifier, int>((ref) {
  return CounterNotifier();
});
```

## 📚 Resources

- [Flutter Docs](https://docs.flutter.dev/)
- [Dart Language Tour](https://dart.dev/guides/language/language-tour)
- [Flutter Widget Catalog](https://docs.flutter.dev/ui/widgets)

---
*Notes by Rushikesh*
