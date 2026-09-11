# EVE rebirth terror 한국어 패치 설치 가이드

현재 기준 버전은 **v1.4.0**입니다.

이 문서는 처음 설치하는 분도 그대로 따라 할 수 있도록 **원본 준비 → 패처 실행 → PC / Android / Nintendo Switch 적용 → 문제 발생 시 확인할 항목** 순서로 정리했습니다.

> [!IMPORTANT]
> **Windows와 Android 모두 Citron Nightly 최신 빌드 사용을 권장합니다.**
>
> v1.4.0은 실행 파일을 직접 교체하는 **direct-main 방식**을 사용합니다. 예전 패치 파일을 남긴 상태에서 덮어쓰기보다 아래 순서대로 새로 적용하는 것을 권장합니다.

---

## 0. 지원 원본 확인

- Base Title ID: `01008BA00F172000`
- Update Title ID: `01008BA00F172800`
- Update: `v131072`
- 게임 표시 버전: `1.0.2`

> [!WARNING]
> **Base만 언팩한 RomFS는 사용할 수 없습니다.**
>
> 반드시 **Base + Update 1.0.2가 함께 반영된 깨끗한 원본**을 사용하세요. 이미 다른 한글패치나 모드가 적용된 원본도 사용하지 않는 것을 권장합니다.

`01008BA00F172800`은 **Update Title ID**입니다. 패처 입력과 실제 모드 폴더에서는 본편 Title ID인 `01008BA00F172000`을 사용합니다.

---

## 1. RomForge로 원본 준비

> [!TIP]
> RomFS 언팩 방법을 이미 알고 있고 Base + Update가 합쳐진 정상 원본이 준비되어 있다면 이 단계는 건너뛰어도 됩니다.

1. RomForge를 실행합니다.
2. 상단 메뉴에서 `Switch` → `리팩` → `파일`로 이동합니다.
3. 본인이 소유한 **EVE rebirth terror Base 파일**과 **Update 1.0.2 파일**을 RomForge에 함께 추가합니다.
4. Output 위치를 지정합니다.
5. `언팩`을 실행합니다.
6. 완료될 때까지 기다립니다.

정상적으로 준비되면 Output 폴더에 `unpacked`가 생성되고, 아래 구조가 존재해야 합니다.

```text
unpacked
└─ 01008BA00F172000
   ├─ exefs
   │  └─ main
   └─ romfs
      └─ data_eve2
```

> [!IMPORTANT]
> 패처에서는 아래 둘 중 하나를 선택할 수 있습니다.
>
> - `unpacked` 폴더
> - `unpacked` 안의 `01008BA00F172000` 폴더

`romfs` 폴더만 따로 선택하는 방식이 아니라 **본편 폴더 또는 unpacked 폴더 전체를 기준으로 검사**합니다.

---

## 2. v1.4.0 패처 실행

1. 배포 ZIP을 원하는 위치에 **완전히 압축 해제**합니다.
2. `EVE-Rebirth-Terror-KR-Patcher.exe`를 실행합니다.
3. **원본 폴더 선택**에서 RomForge의 `unpacked` 또는 `01008BA00F172000` 폴더를 선택합니다.
4. 패처가 원본 Title ID와 필요한 파일을 정상적으로 확인하는지 확인합니다.
5. **출력 위치**를 선택합니다.
6. `한국어 패치 시작`을 누릅니다.
7. 원본 검사 → 패치 적용 → 결과 검사가 끝날 때까지 기다립니다.

패처는 준비한 원본을 직접 덮어쓰지 않고 별도의 결과물을 생성합니다.

정상 완료 시 다음 세 폴더가 만들어집니다.

```text
EVE-Rebirth-Terror-KR-v1.4.0-PC
EVE-Rebirth-Terror-KR-v1.4.0-Android
EVE-Rebirth-Terror-KR-v1.4.0-Switch
```

각 폴더는 **용도가 다르므로 사용하는 환경에 맞는 결과물만 적용**하면 됩니다.

---

## 3. 결과물 구조

### PC용

```text
EVE-Rebirth-Terror-KR-v1.4.0-PC
├─ exefs
│  └─ main
└─ romfs
   └─ data_eve2
```

### Android용

```text
EVE-Rebirth-Terror-KR-v1.4.0-Android
└─ 01008BA00F172000
   ├─ exefs
   │  └─ main
   └─ romfs
      └─ data_eve2
```

### Nintendo Switch용

```text
EVE-Rebirth-Terror-KR-v1.4.0-Switch
└─ atmosphere
   └─ contents
      └─ 01008BA00F172000
         ├─ exefs
         │  └─ main
         └─ romfs
            └─ data_eve2
```

> [!NOTE]
> v1.4.0은 실행 파일을 직접 교체하는 **direct-main 방식**입니다. 별도의 IPS 또는 pchtxt 설치는 필요하지 않습니다.

---

# 4. PC 적용 방법

## Citron Windows Nightly

> [!TIP]
> **권장 버전: Citron Windows Nightly 최신 빌드**

사용하는 폴더:

```text
EVE-Rebirth-Terror-KR-v1.4.0-PC
```

### 적용 순서

1. Citron에서 `EVE rebirth terror`를 찾습니다.
2. 게임을 **우클릭**합니다.
3. `Open Mod Data Location` 또는 **모드 데이터 위치 열기**를 선택합니다.
4. 열린 폴더 안에 패처가 생성한 **`EVE-Rebirth-Terror-KR-v1.4.0-PC` 폴더 자체를 통째로 복사**합니다.
5. 복사 후 아래처럼 보이면 정상입니다.

```text
user
└─ load
   └─ 01008BA00F172000
      └─ EVE-Rebirth-Terror-KR-v1.4.0-PC
         ├─ exefs
         │  └─ main
         └─ romfs
            └─ data_eve2
```

6. Citron을 다시 실행하거나 게임 목록을 새로고침한 뒤 게임을 시작합니다.
7. 타이틀 화면과 게임 내 대사가 한국어로 표시되는지 확인합니다.

<img width="214" height="251" alt="Citron Windows 모드 데이터 위치 열기" src="https://github.com/user-attachments/assets/79b14a04-e304-42ba-8e91-59eac659f5da" />

> [!IMPORTANT]
> **`exefs`와 `romfs`만 꺼내서 `01008BA00F172000` 바로 아래에 넣는 것이 아닙니다.**
>
> `Open Mod Data Location`으로 열린 위치에 **`EVE-Rebirth-Terror-KR-v1.4.0-PC` 폴더 자체를 넣으면 됩니다.**

---

# 5. Android 적용 방법

## Citron Android Nightly

> [!TIP]
> **권장 버전: Citron Android Nightly 최신 빌드**

사용하는 폴더:

```text
EVE-Rebirth-Terror-KR-v1.4.0-Android
└─ 01008BA00F172000
```

### 방법 A. Citron의 Add-ons 기능으로 적용

Android 11 이상에서는 파일 관리 앱으로 `Android/data` 내부를 직접 수정하는 것보다 **Citron의 Add-ons 설치 기능을 사용하는 것을 권장**합니다.

1. Citron에서 `EVE rebirth terror`의 게임 설정 또는 속성을 엽니다.
2. `Add-ons` 메뉴로 이동합니다.
3. `+` 또는 설치 버튼을 누릅니다.
4. 콘텐츠 종류에서 **Mod / 모드**를 선택합니다.
5. 패처가 만든 Android 결과물의 `01008BA00F172000` 폴더를 지정합니다.
6. 설치가 끝나면 Add-ons 목록에서 EVE rebirth terror용 모드가 활성화되어 있는지 확인합니다.
7. 게임을 실행해 한국어 적용 여부를 확인합니다.

<img width="80%" alt="Citron Android Add-ons 설치 화면" src="https://github.com/user-attachments/assets/81851895-b9e9-47e0-8915-12010f439d56" />

<img width="80%" alt="Citron Android 모드 선택 화면" src="https://github.com/user-attachments/assets/47bb1aaf-11e7-4c07-9cfa-bd4807f4d030" />

### 방법 B. 모드 폴더에 직접 복사

직접 복사가 가능한 환경에서는 Android 결과물 안의 `01008BA00F172000` 폴더를 Citron의 `load` 위치에 넣어도 됩니다.

일반적인 위치는 다음과 같습니다.

```text
/storage/emulated/0/Android/data/org.citron.citron_emu/files/load/
└─ 01008BA00F172000
   ├─ exefs
   │  └─ main
   └─ romfs
      └─ data_eve2
```

최종적으로 아래 두 경로가 함께 존재해야 합니다.

```text
01008BA00F172000/exefs/main
01008BA00F172000/romfs/data_eve2
```

> [!IMPORTANT]
> **v1.4.0에서 Android 실행 문제를 수정했습니다.**
>
> 현재 **Odin2 Portal에서 정상 실행을 확인**했습니다.

> [!WARNING]
> 기존에 사용하던 구버전 모드가 남아 있다면 먼저 제거한 뒤 v1.4.0 결과물만 설치하는 것을 권장합니다.

---

# 6. Nintendo Switch 실기 적용 방법

## Atmosphere

사용하는 폴더:

```text
EVE-Rebirth-Terror-KR-v1.4.0-Switch
└─ atmosphere
```

> [!CAUTION]
> **기존 Switch 한글패치 위에 그대로 덮어쓰지 마세요.**
>
> 구버전 파일이 남아 있으면 새 direct-main 파일과 충돌해 게임이 실행되지 않을 수 있습니다.

### 적용 순서

1. Switch의 전원을 끄고 SD 카드를 PC에 연결합니다.
2. 아래 기존 모드 폴더가 있다면 **삭제하거나 내부를 완전히 비웁니다.**

```text
SD:/atmosphere/contents/01008BA00F172000
```

3. 패처가 생성한 Switch 결과물 안의 `atmosphere` 폴더를 SD 카드 **최상위 루트**에 복사합니다.
4. 기존 `atmosphere` 폴더가 있다면 정상적으로 병합합니다.
5. 복사가 끝난 뒤 아래 경로를 확인합니다.

```text
SD:/atmosphere/contents/01008BA00F172000/exefs/main
SD:/atmosphere/contents/01008BA00F172000/romfs/data_eve2/...
```

6. SD 카드를 Switch에 다시 넣습니다.
7. **Switch 본체를 완전히 재부팅**합니다.
8. 게임을 실행해 한국어 적용 여부를 확인합니다.

> [!WARNING]
> `01008BA00F172000` 폴더를 SD 카드 루트에 바로 넣는 것이 아닙니다.
>
> 반드시 `SD:/atmosphere/contents/01008BA00F172000/` 구조가 되어야 합니다.

---

# 7. 패치가 적용되지 않을 때 확인

아래 항목을 순서대로 확인해 주세요.

1. **게임 버전이 1.0.2인지 확인**
2. RomForge 원본에 **Base + Update가 함께 반영**되어 있는지 확인
3. 다른 한글패치 또는 모드가 섞인 원본을 사용하지 않았는지 확인
4. PC에서는 `Open Mod Data Location`으로 열린 `01008BA00F172000` 폴더 안에 **`EVE-Rebirth-Terror-KR-v1.4.0-PC` 폴더 자체가 들어가 있는지 확인**
5. Android에서는 `01008BA00F172000/exefs/main`과 `romfs/data_eve2`가 함께 있는지 확인
6. Switch에서는 구버전 `01008BA00F172000` 폴더를 먼저 비웠는지 확인
7. Switch 적용 후 **완전 재부팅**했는지 확인

패처가 원본 검사 단계에서 중단된다면 파일을 억지로 바꾸기보다 **깨끗한 Base + Update 원본부터 다시 준비하는 것을 권장**합니다.

---

# 확인된 호환성

- **PC:** Citron Windows에서 정상 작동 확인
- **Android:** Odin2 Portal에서 정상 실행 확인
- **Nintendo Switch 실기:** 정상 작동 확인

---

# 주의사항

- 본인이 소유한 게임과 키로 준비한 원본을 사용하세요.
- 패처는 잘못된 Title ID, 버전 또는 수정된 원본을 발견하면 중단할 수 있습니다.
- 배포물에는 원본 게임, 전체 RomFS, 완성된 `main`, NSP/XCI/NCA, `prod.keys`가 포함되지 않습니다.
