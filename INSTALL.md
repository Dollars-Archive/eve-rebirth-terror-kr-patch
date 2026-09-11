# EVE rebirth terror 한국어 패치 설치 가이드

이 문서는 **설치 방법을 한곳에서 관리하기 위한 공용 설치 가이드**입니다.

앞으로 각 Release에는 해당 버전의 변경 사항과 호환성만 간단히 적고, 실제 설치 방법은 이 문서를 기준으로 안내합니다.

---

## 지원 원본

- Base Title ID: `01008BA00F172000`
- 본편 버전: `v0`
- Update Title ID: `01008BA00F172800`
- 업데이트 버전: `v131072`
- 게임 표시 버전: `1.0.2`

원본 파일 식별용 MD5:

- 본편 v0  
  `0F262016E3653174090EEA96379E0BE6`

- 업데이트 1.0.2  
  `0E605AA5B0C65682A8CBC6136529BCFC`

> [!IMPORTANT]
> **본편만 추출한 RomFS는 사용할 수 없습니다.**  
> 반드시 **본편 + 업데이트 1.0.2가 함께 적용된 RomFS**가 필요합니다.

---

## 1. RomForge로 RomFS 준비

> [!TIP]
> **RomFS 덤프 방법을 이미 알고 계신다면 이 과정은 건너뛰셔도 됩니다.**

1. RomForge를 실행합니다.
2. 상단 메뉴에서 `Switch` → `리팩` → `파일`로 이동합니다.
3. **EVE rebirth terror 본편 파일과 업데이트 1.0.2 파일**을 RomForge 창으로 드래그합니다.
4. 우측 하단의 **폴더 아이콘**을 눌러 Output 위치를 지정합니다.
5. 하단의 **`언팩`** 버튼을 누릅니다.
6. 언팩이 완료될 때까지 기다립니다.

정상적으로 불러왔다면 RomForge에 아래 두 항목이 표시됩니다.

```text
Base   : 01008BA00F172000 / 1.0.0
Update : 01008BA00F172800 / 1.0.2
```

언팩이 완료되면 지정한 Output 위치에 아래 폴더들이 생성됩니다.

```text
build_nca
temp
unpacked
```

---

## 2. 한국어 패치 적용

1. 배포 ZIP을 완전히 압축 해제합니다.
2. `EVE-Rebirth-Terror-KR-Patcher.exe`를 실행합니다.
3. `[폴더 선택]`을 누릅니다.
4. RomForge에서 언팩한 아래 `romfs` 폴더를 선택합니다.

```text
unpacked\01008BA00F172000\romfs
```

5. 화면에 `패치를 시작할 수 있습니다.`가 표시되는지 확인합니다.
6. `[한국어 패치 시작]`을 누릅니다.
7. 원본 검증 → 패치 적용 → 결과 검증이 자동으로 진행됩니다.

패치가 완료되면 패처 폴더 안에 PC용과 Switch·Android용 결과 폴더가 생성됩니다.

```text
EVE-Rebirth-Terror-KR-vX.Y.Z-Patcher
├─ EVE-Rebirth-Terror-KR-vX.Y.Z-PC
└─ EVE-Rebirth-Terror-KR-vX.Y.Z-Switch-Android
```

`vX.Y.Z` 부분은 설치한 패치 버전에 따라 달라집니다.

---

## 3. PC 설치

### Citron Windows

> [!TIP]
> **권장 버전: Citron Windows Nightly**  
> 기존 검수는 **260807 버전**에서 진행했습니다.

패처가 생성한 **PC용 결과 폴더**를 사용합니다.

게임 우클릭 → `Open Mod Data Location`을 연 뒤 해당 패치 폴더를 적용합니다.

---

## 4. Android 설치

### Citron Android Nightly

> [!WARNING]
> ### Android판 실행 관련 중요 안내
> 현재 패치는 **PC와 Nintendo Switch 실기에서만 정상 작동을 확인**했습니다.  
> Android 환경에서는 **게임이 실행되지 않는 문제가 있어 현재 원인을 조사 중**입니다.
>
> **Android에서 플레이하실 분들은 현재 버전 적용을 보류하고, 수정된 다음 패치가 배포된 뒤 이용해 주세요.**

패처가 생성한 `EVE-Rebirth-Terror-KR-vX.Y.Z-Switch-Android` 폴더를 사용합니다.

게임 속성 → `Add-ons` → 설치 또는 `+` → `Mod`에서 해당 폴더를 선택합니다.

일반적인 내부 적용 위치:

`/storage/emulated/0/Android/data/org.citron.citron_emu/files/load/`  
`└─ 01008BA00F172000`  
`   └─ EVE-Rebirth-Terror-KR`  
`      └─ romfs`  
`         └─ data_eve2`

Android 11 이상에서는 직접 경로에 복사하는 것보다 Citron의 **Add-ons 설치 기능** 사용을 권장합니다.

---

## 5. Nintendo Switch 실기 설치

### Atmosphere

> [!IMPORTANT]
> ## Switch 설치는 폴더 2개를 각각 다른 위치에 복사합니다
>
> 패처 실행이 끝나면 **Switch·Android용 결과 폴더** 안의 아래 두 폴더를 사용합니다.
>
> ```text
> 01008BA00F172000
> atmosphere
> ```
>
> **`01008BA00F172000` 폴더와 `atmosphere` 폴더는 복사 위치가 서로 다릅니다.**

### 1단계: `01008BA00F172000` 폴더 복사

결과물의 **`01008BA00F172000` 폴더를 통째로** 아래 위치에 복사합니다.

```text
SD:/atmosphere/contents/
```

복사가 끝나면 아래처럼 되어 있어야 합니다.

```text
SD카드
└─ atmosphere
   └─ contents
      └─ 01008BA00F172000
         └─ romfs
```

### 2단계: `atmosphere` 폴더 복사

결과물의 **`atmosphere` 폴더를 SD카드 최상위(루트)에 복사**합니다.

```text
SD:/
```

이미 SD카드에 `atmosphere` 폴더가 있다면 **기존 폴더와 병합해서 복사**하면 됩니다.

이 폴더에는 리버스 테러용 `exefs_patches`가 포함되어 있으므로, `01008BA00F172000` 폴더만 복사하고 끝내면 안 됩니다.

### 3단계: Switch 완전 재부팅

두 폴더를 모두 복사했으면 SD카드를 Switch에 넣고 **본체를 완전히 재부팅**한 뒤 게임을 실행합니다.

> [!WARNING]
> - `01008BA00F172000` 폴더를 SD카드 루트에 바로 넣으면 안 됩니다.
> - `atmosphere` 폴더를 `contents` 안에 넣으면 안 됩니다.
> - `01008BA00F172000`은 반드시 `SD:/atmosphere/contents/` 아래에 있어야 합니다.
> - 결과물의 `atmosphere` 폴더도 반드시 SD카드 루트에 병합 복사해야 합니다.

최종적으로 아래 구조가 존재해야 합니다.

```text
SD:/atmosphere/contents/01008BA00F172000/romfs

SD:/atmosphere/exefs_patches/EVE-Rebirth-Terror-KR-vX.Y.Z/
└─ 5841D3A4F38CF54DC99E54F137776FF530D2EFF2000000000000000000000000.ips
```

정리하면 아래 두 줄만 기억하면 됩니다.

```text
01008BA00F172000  →  SD:/atmosphere/contents/
atmosphere        →  SD:/
```

---

## 주의사항

- 본인이 소유한 게임에서 직접 준비한 원본을 사용하세요.
- 이미 다른 패치나 모드가 적용된 RomFS는 사용할 수 없습니다.
- 기존 결과 폴더가 존재하면 패처가 덮어쓰지 않고 중단합니다.

본 배포본에는 **게임 본편 및 원본 게임 데이터, 원본 RomFS, 키 파일 또는 완성 게임 파일이 포함되어 있지 않습니다.**
