# EVE rebirth terror 한국어 패치 설치 가이드

현재 기준 버전은 **v1.4.0**입니다. 패처는 사용자가 준비한 RomForge 원본에서 PC·Android·Nintendo Switch 결과물을 한 번에 만듭니다.

## 지원 원본

- Base Title ID: `01008BA00F172000`
- Update Title ID: `01008BA00F172800`
- Update: `v131072` / 게임 버전 `1.0.2`

> [!IMPORTANT]
> 패치에는 반드시 Base와 Update가 함께 반영된 깨끗한 원본이 필요합니다.
> 이미 다른 패치나 모드가 적용된 원본은 사용하지 마세요.

## 1. RomForge 원본 준비

1. 본인이 소유한 Base와 Update v131072를 RomForge로 언팩합니다.
2. Base와 Update가 함께 반영된 `unpacked` 폴더를 준비합니다.
3. 패처에서는 `unpacked` 폴더 또는 그 안의 `01008BA00F172000` 폴더를 선택합니다.

정상 구조는 다음과 같습니다.

```text
unpacked
└─ 01008BA00F172000
   ├─ exefs
   │  └─ main
   └─ romfs
      └─ data_eve2
```

> [!WARNING]
> `01008BA00F172800`은 Update Title ID입니다. 패처와 Switch 모드 폴더에는 반드시 `01008BA00F172000`을 사용하세요.

## 2. v1.4.0 패처 실행

1. 배포 ZIP을 완전히 압축 해제합니다.
2. `EVE-Rebirth-Terror-KR-Patcher.exe`를 실행합니다.
3. RomForge의 `unpacked` 폴더 또는 `01008BA00F172000` 폴더를 선택합니다.
4. 출력 위치를 선택하고 **한국어 패치 시작**을 누릅니다.

패처는 원본을 직접 수정하지 않고, 원본 검사와 결과 검사를 통과한 경우에만 세 결과 폴더를 생성합니다.

```text
EVE-Rebirth-Terror-KR-v1.4.0-PC
EVE-Rebirth-Terror-KR-v1.4.0-Android
EVE-Rebirth-Terror-KR-v1.4.0-Switch
```

## 3. 결과물 구조

```text
PC
├─ exefs
│  └─ main
└─ romfs
   └─ data_eve2

Android
└─ 01008BA00F172000
   ├─ exefs
   │  └─ main
   └─ romfs
      └─ data_eve2

Switch
└─ atmosphere
   └─ contents
      └─ 01008BA00F172000
         ├─ exefs
         │  └─ main
         └─ romfs
            └─ data_eve2
```

v1.4.0은 실행 파일을 직접 교체하는 **direct-main** 방식입니다. IPS나 pchtxt를 따로 설치하지 않습니다.

## 4. PC Eden 설치

PC 결과 폴더의 `exefs`와 `romfs`를 게임의 모드 데이터 위치에 함께 복사합니다.

## 5. Android Eden / Odin2 Portal 설치

Android 결과 안의 `01008BA00F172000` 폴더를 Eden의 `load` 또는 게임별 모드 위치에 복사합니다.

최종적으로 `01008BA00F172000\exefs\main`과 `01008BA00F172000\romfs\data_eve2`가 함께 있어야 합니다.

> [!IMPORTANT]
> **Android 실행 문제 해결 완료**
>
> v1.4.0은 Android 실행 문제를 수정했으며, **Odin2 Portal에서 정상 실행을 확인했습니다.**

## 6. Nintendo Switch 실기 설치

> [!WARNING]
> **기존 Switch 모드에 덮어쓰면 안 됩니다.** 이전 파일이 남아 있으면 충돌로 게임이 실행되지 않을 수 있습니다.

1. SD 카드에서 기존 `SD:/atmosphere/contents/01008BA00F172000` 폴더를 삭제하거나 내용물을 모두 비웁니다.
2. 패처의 Switch 결과 안에 있는 `atmosphere` 폴더를 SD 카드 최상위에 새로 복사합니다.
3. Switch를 완전히 재부팅한 뒤 게임을 실행합니다.

최종 경로는 다음과 같아야 합니다.

```text
SD:/atmosphere/contents/01008BA00F172000/exefs/main
SD:/atmosphere/contents/01008BA00F172000/romfs/data_eve2/...
```

## 확인된 호환성

- **PC:** 정상 작동 확인
- **Android:** Odin2 Portal 정상 실행 확인
- **Nintendo Switch 실기:** 정상 작동 확인

## 주의사항

- 본인이 소유한 게임과 키로 준비한 원본을 사용하세요.
- 패처는 잘못된 Title ID, 버전 또는 수정된 원본을 발견하면 중단합니다.
- 배포물에는 원본 게임, 전체 RomFS, 완성된 main, NSP/XCI/NCA, prod.keys가 포함되지 않습니다.