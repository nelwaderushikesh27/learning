# React Native Notes

## 📌 Key Concepts

### What is React Native?
A framework for building native apps using React and JavaScript/TypeScript.

## 🚀 Creating a React Native App

```bash
npx react-native init MyApp --template react-native-template-typescript
cd MyApp
npx react-native run-android
```

## 📦 Core Components

| Component | Android | iOS | Web |
|-----------|---------|-----|-----|
| `<View>` | `ViewGroup` | `UIView` | `<div>` |
| `<Text>` | `TextView` | `UITextView` | `<p>` |
| `<ScrollView>` | `ScrollView` | `UIScrollView` | Scroll |
| `<TextInput>` | `EditText` | `UITextField` | `<input>` |

## 🧩 Basic Component

```typescript
interface Props {
  title: string;
  onPress: () => void;
}

const MyButton: React.FC<Props> = ({ title, onPress }) => {
  return (
    <TouchableOpacity
      style={styles.button}
      onPress={onPress}
      activeOpacity={0.8}
    >
      <Text style={styles.text}>{title}</Text>
    </TouchableOpacity>
  );
};

const styles = StyleSheet.create({
  button: {
    backgroundColor: '#6366F1',
    padding: 16,
    borderRadius: 8,
    alignItems: 'center',
  },
  text: {
    color: '#FFFFFF',
    fontSize: 16,
    fontWeight: '600',
  },
});
```

## 🗺️ Navigation

```typescript
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';

const Stack = createNativeStackNavigator();

const App = () => (
  <NavigationContainer>
    <Stack.Navigator>
      <Stack.Screen name="Home" component={HomeScreen} />
      <Stack.Screen name="Details" component={DetailsScreen} />
    </Stack.Navigator>
  </NavigationContainer>
);
```

## 🔄 State Management

### Redux Toolkit
```typescript
import { createSlice, configureStore } from '@reduxjs/toolkit';

const todosSlice = createSlice({
  name: 'todos',
  initialState: [],
  reducers: {
    addTodo: (state, action) => {
      state.push(action.payload);
    },
  },
});

const store = configureStore({
  reducer: { todos: todosSlice.reducer },
});
```

## 📚 Resources

- [React Native Docs](https://reactnative.dev/)
- [Expo Docs](https://docs.expo.dev/)
- [React Navigation](https://reactnavigation.org/)

---
*Notes by Rushikesh*
