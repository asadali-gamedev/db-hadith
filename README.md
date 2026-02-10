# Hadith API

Free API to download complete Hadith database collections (SQLite).

## 📚 Available Books

| Book | Size |
|------|------|
| Sahih Bukhari | 41.7 MB |
| Sahih Muslim | 30.1 MB |
| Sunan Abu Dawood | 28.1 MB |
| Jami at-Tirmidhi | 26.9 MB |
| Sunan an-Nasai | 23.0 MB |
| Sunan Ibn Majah | 20.5 MB |
| Mishkat al-Masabih | 15.3 MB |
| Musnad Ahmad | 71.7 MB |
| Silsila Sahiha | 9.1 MB |

## 🔗 API Endpoint

```
GET https://asadali-gamedev.github.io/db-hadith/api/books.json
```

## 📥 Download Databases

Each database is available from GitHub Releases:
```
https://github.com/asadali-gamedev/db-hadith/releases/download/v1.0.0/bukhari.db
```

## 🗄️ Database Schema

Each `.db` file contains:
- `hadees` - Arabic text, hadith number, status, volume
- `hadees_languages` - Translations (Urdu, English, Hindi, Roman) + baab, kitab, ravi, takhreej, wazahat
- `tbl_Kitab` - Book chapters
- `language` - Available languages

## 📱 Usage

```dart
// Fetch book list
final response = await http.get('https://asadali-gamedev.github.io/db-hadith/api/books.json');
final data = jsonDecode(response.body);

// Download a specific database
final bukhari = data['books'].firstWhere((b) => b['id'] == 'bukhari');
// Use bukhari['downloadUrl'] to download the file
```
