# mylist

[العربية](#العربية) | [English](#english)

## العربية

### نبذة

`mylist` هي قائمة تشغيل صغيرة بصيغة Extended M3U تضم 20 قناة رياضية. توفر القائمة بيانات القنوات وروابط بث خارجية، ولا تتضمن مشغّل فيديو ولا تستضيف أي محتوى مرئي.

### محتوى القائمة

- 10 إدخالات ضمن مجموعة `beIN Sports`.
- 10 إدخالات ضمن مجموعة `VODO`، تشمل قنوات Thmanyah وAl Iraqia Sports وAlkass وAD Sports.
- يشير كل إدخال إلى بث HTTPS خارجي بصيغة `.m3u8`.

### الصيغة

تستخدم القائمة توجيهات Extended M3U الآتية:

- يعرّف `#EXTM3U` صيغة قائمة التشغيل.
- يحدد `#EXTINF` اسم القناة.
- يحدد `#EXTGRP` مجموعة القناة.
- يحتوي السطر التالي على رابط البث الخارجي.

### هيكل المشروع

```text
.
├── Mylist.m3u8  # قائمة قنوات رياضية بصيغة Extended M3U
└── README.md
```

### استخدام القائمة

افتح `Mylist.m3u8` في مشغّل أو تطبيق IPTV يدعم قوائم Extended M3U وبث HLS. على سبيل المثال، إذا كان VLC أو mpv مثبتاً:

```bash
vlc Mylist.m3u8
```

أو:

```bash
mpv Mylist.m3u8
```

يعتمد التشغيل على خوادم البث الخارجية واتصال الشبكة وإمكانات المشغّل المستخدم.

### إضافة إدخال أو تحديثه

حافظ على الصيغة الآتية لكل عنصر:

```m3u
#EXTINF:-1,Channel Name
#EXTGRP:Group Name
https://example.com/path/stream.m3u8
```

استخدم فقط روابط البث التي يُسمح لك بالوصول إليها وإعادة توزيعها.

### الحالة الحالية

هذه نسخة بيانات ثابتة لقائمة تشغيل فقط. لا يوجد كود تطبيق أو عملية بناء أو فحص آلي لتوفر البث أو مشغّل مضمّن. لا يتحكم المستودع بالخوادم الخارجية، لذلك قد تتغير بعض التدفقات أو تتوقف عن العمل.

يوجد في الملف الحالي سطر فارغ قبل ترويسة `#EXTM3U`. تتسامح مشغّلات كثيرة مع ذلك، لكن بعض المحللات الصارمة قد تشترط أن تكون `#EXTM3U` في السطر الأول.

## English

### Overview

`mylist` is a small Extended M3U playlist containing 20 sports channel entries. It provides channel metadata and external stream URLs; it does not include a video player or host any media.

### Playlist contents

- 10 entries in the `beIN Sports` group.
- 10 entries in the `VODO` group, including Thmanyah, Al Iraqia Sports, Alkass, and AD Sports channels.
- Every entry points to an external HTTPS `.m3u8` stream.

### Format

The playlist uses these Extended M3U directives:

- `#EXTM3U` declares the playlist format.
- `#EXTINF` provides the channel name.
- `#EXTGRP` assigns the channel group.
- The following line contains the external stream URL.

### Project structure

```text
.
├── Mylist.m3u8  # Extended M3U sports playlist
└── README.md
```

### Use the playlist

Open `Mylist.m3u8` in a player or IPTV application that supports Extended M3U playlists and HLS streams. For example, if VLC or mpv is installed:

```bash
vlc Mylist.m3u8
```

or:

```bash
mpv Mylist.m3u8
```

Playback depends on the external stream hosts, your network connection, and the capabilities of the selected player.

### Add or update an entry

Keep each item in this form:

```m3u
#EXTINF:-1,Channel Name
#EXTGRP:Group Name
https://example.com/path/stream.m3u8
```

Use only stream URLs that you are allowed to access and redistribute.

### Current status

This is a data-only playlist snapshot. There is no application code, build process, automated availability check, or bundled player. The repository does not control the external servers, so individual streams may change or stop working.

The current file has a blank line before the `#EXTM3U` header. Many players tolerate it, but strict parsers may require `#EXTM3U` to be the first line.
