# Melalui Service Android TV

## Download APK dari Android TV ke Home Assistant

```
service: androidtv.download
data:
  entity_id: media_player.android_tv_2
  device_path: /sdcard/Download/apk/dutafilm.apk
  local_path: /config/www/dutafilm.apk
```

## Upload APK dari Home Assistant ke Android TV

```
service: androidtv.upload
data:
  entity_id: media_player.android_tv_2
  device_path: /sdcard/Download/apk/dutafilm.apk
  local_path: /config/www/dutafilm.apk
```

## Install APK di Android TV dari Home Assistant

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
	pm install -r /sdcard/Download/apk/dutafilm.apk
```

## Youtube

### Menjalankan Youtube

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -d -n
    com.google.android.youtube.tv/com.google.android.apps.youtube.tv.activity.ShellActivity
```

### Menjalankan Video di Youtube

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -d 'https://youtu.be/ussCHoQttyQ' -n
    com.google.android.youtube.tv/com.google.android.apps.youtube.tv.activity.ShellActivity
```

### Menghentikan Youtube

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.google.android.youtube.tv
```

## Youtube Kids

### Menjalankan Youtube Kids

```
service: androidtv.adb_command
data:
  command: >-
    am start -a android.intent.action.VIEW -d -n
    com.google.android.youtube.tvkids/com.google.android.apps.youtube.tvkids.activity.MainActivity
  entity_id: media_player.android_tv_2
```

### Manghentikan Youtube Kids

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.google.android.youtube.tvkids
```
## Spotify

### Menjalankan Spotify

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -n
    com.spotify.tv.android/.SpotifyTVActivity
```

### Menghentikan Spotify

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.spotify.tv.android
```

## Netflix

### Menjalankan Netflix

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: am start -a android.intent.action.VIEW -n com.netflix.ninja/.MainActivity
```

### Memutar Movie/Serial di Netflix

Contoh Serial **HOSPITAL PLAYLIST** yang memiliki URL https://www.netflix.com/watch/81413568 dapat di putar ke *Android TV* melalui perintah berikut:

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -n com.netflix.ninja/.MainActivity -a android.intent.action.VIEW -d
    netflix://title/81413568 -f 0x10000020 -e "amzn_deeplink_data" "81413568"
```

### Menghentikan Netflix

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.netflix.ninja
```

## VIU

### Menjalankan VIU

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -n
    com.vuclip.viu.tv/com.vuclip.viu.view.splash.TvSplashActivity
```

### Menghentikan VIU

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.vuclip.viu.tv
```

## IQIYI

### Menjalankan IQIYI

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -n
    com.iqiyi.i18n.tv/.launch.LaunchActivity
```

### Menghentikan IQIYI

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.iqiyi.i18n.tv
```

## Disney+ Hotstar

### Menjalankan Disney+ Hotstar

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -n
    in.startv.hotstar.dplus.tv/in.startv.hotstar.ui.splash.TVSplashActivity
```

### Menghentikan Disney+ Hotstar

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    in.startv.hotstar.dplus.tv
```

## Vidio

### Menjalankan Vidio

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -n
    com.vidio.android.tv/.splashscreen.SplashScreenActivity
```

### Menghentikan Vidio

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.vidio.android.tv
```

## UseeTV

### Menjalankan UseeTV

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -n
    com.useetv.stb/.presentation.splashscreen.SplashScreenActivity
```

### Menghentikan UseeTV

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.useetv.stb
```

## IPTV Pro

### Menjalankan IPTV Pro

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -n
    ru.iptvremote.android.iptv.pro/.ChannelsActivity
```

### Menghentikan IPTV Pro

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    ru.iptvremote.android.iptv.pro
```

## TinyCam FREE

### Menjalankan TinyCam FREE

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -n
    com.alexvas.dvr/.MainActivity
```

### Menghentikan TinyCam FREE

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.alexvas.dvr
```

## DutaFilm

### Menjalankan DutaFilm

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am start -a android.intent.action.VIEW -d -n
    com.dutafilm.online/.MainActivity
```

### Menghentikan DutaFilm

```
service: androidtv.adb_command
data:
  entity_id: media_player.android_tv_2
  command: >-
    am force-stop
    com.dutafilm.online
```

# Melalui Service Media Player

```
service: media_player.select_source
target:
  entity_id: media_player.android_tv_2
data:
  source: Netflix/Spotify/HBO Go
```

* Informasi lainnya di *https://gist.github.com/atoz-chevara/2a052ae2ef7cbae9e6991aaca9000f33*
