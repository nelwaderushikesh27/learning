# Room Database Notes

## 📌 Key Concepts

### What is Room?
Room is a persistence library for Android that provides an abstraction layer over SQLite.

## 🚀 Setup

```kotlin
dependencies {
    implementation "androidx.room:room-runtime:2.6.1"
    implementation "androidx.room:room-ktx:2.6.1"
    ksp "androidx.room:room-compiler:2.6.1"
}
```

## 📦 Entity

```kotlin
@Entity(tableName = "users")
data class User(
    @PrimaryKey(autoGenerate = true)
    val id: Long = 0,
    @ColumnInfo(name = "full_name")
    val name: String,
    val email: String,
    val age: Int = 0
)
```

## 🔍 DAO

```kotlin
@Dao
interface UserDao {
    @Query("SELECT * FROM users")
    fun getAll(): Flow<List<User>>
    
    @Insert
    suspend fun insert(user: User): Long
    
    @Update
    suspend fun update(user: User)
    
    @Delete
    suspend fun delete(user: User)
}
```

## 🏗️ Database

```kotlin
@Database(entities = [User::class], version = 1)
abstract class AppDatabase : RoomDatabase() {
    abstract fun userDao(): UserDao
    
    companion object {
        @Volatile
        private var INSTANCE: AppDatabase? = null
        
        fun getInstance(context: Context): AppDatabase {
            return INSTANCE ?: synchronized(this) {
                Room.databaseBuilder(
                    context,
                    AppDatabase::class.java,
                    "app_database"
                ).build().also { INSTANCE = it }
            }
        }
    }
}
```

## 📚 Resources

- [Official Docs](https://developer.android.com/training/data-storage/room)

---
*Notes by Rushikesh*
