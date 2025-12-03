Offline Sync Mobile Library

A comprehensive Flutter package for offline data synchronization with
remote APIs, featuring real-time WebSocket support, automatic conflict
resolution, and customizable options.

[Step-By-Step Guide to Build a Flutter Offline Sync Library.](https://www.sevensquaretech.com/build-flutter-offline-sync-library-github-code/)

🚀 Features

- Offline‑first architecture
- Automatic background sync when network is restored
- Real‑time WebSocket sync support
- Conflict resolution system
- Queue-based request execution
- Local storage using Isar + Sqflite
- Data encryption support
- Works on Android, iOS, macOS, Windows

📦 Installation

Add the package to your pubspec.yaml:

    dependencies:
      offline_sync_mobile_library: ^1.5.3

Run:

    flutter pub get

🛠 Dependencies

This package uses: - sqflite - isar - connectivity_plus - http - uuid -
rxdart - encrypt - crypto

📚 Basic Usage

    final sync = OfflineSyncManager(
      apiBaseUrl: "https://your-api.com",
      enableWebSocket: true,
      encryptionKey: "YOUR_KEY",
    );

    // Save data locally and sync later
    await sync.save("users", {"name": "John", "age": 25});

    // Force manual sync
    await sync.syncNow();

🌐 WebSocket Sync

    sync.enableWebSocketSync(
      url: "wss://your-api.com/socket",
      channel: "sync_updates",
    );

⚙️ Conflict Resolution

The library provides auto‑strategy: - Client‑always‑wins -
Server‑always‑wins - Timestamp‑based merge

Custom handler example:

    sync.setConflictResolver((local, remote) {
      return {...remote, "merged": true};
    });

🏗 Build Scripts

Run generators:

    dart run build_runner build

🔗 GitHub

https://github.com/SevenSquare-Tech/offline_sync_mobile_library
