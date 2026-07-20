# pulse_simul — 릴리스 / 웹 플래셔

속도 펄스 시뮬레이터(JIS D 5601, ESP32-S3) 펌웨어의 **공개 배포 저장소**입니다.
소스 코드는 비공개이며, 이 저장소에는 빌드된 바이너리와 웹 플래셔만 배포됩니다.

## 🌐 웹 플래셔 (브라우저에서 바로 설치)

👉 **https://firepooh.github.io/pulse_simul-releases/**

- 데스크톱 **Chrome / Edge** 에서 열고, USB 케이블로 ESP32-S3 보드를 연결하세요.
- `연결(Connect)` → 버전 선택 → `플래시(Flash 0x0)` 순서로 진행합니다.
- `merged.bin` 은 0x0 부터 부트로더·파티션·앱이 모두 포함된 단일 이미지입니다.

## 📦 수동 플래시 (esptool)

[Releases](https://github.com/firepooh/pulse_simul-releases/releases) 에서 `*-merged.bin` 을 받아:

```
esptool --chip esp32s3 -p <PORT> write_flash 0x0 pulse_simul-esp32s3-vX.Y.Z-merged.bin
```

## 📁 구성

| 경로 | 내용 |
|---|---|
| `index.html` | ESP Web Tools(esptool-js) 기반 웹 플래셔 |
| `manifest.json` | 웹 플래셔가 읽는 버전 목록 (최신순) |
| `firmware/` | 버전별 merged.bin |

> 바이너리는 소스 저장소(`pulse_simul`, 비공개)의 `v*` 태그 빌드에서 자동 배포됩니다.
