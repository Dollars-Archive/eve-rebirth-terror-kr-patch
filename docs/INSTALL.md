# EVE rebirth terror 한국어 패치 설치 가이드

현재 기준 버전은 **v1.4.0**입니다.

이 문서는 **Nintendo Switch 실기 적용 방법만** 안내합니다.

> [!IMPORTANT]
> v1.4.0은 실행 파일을 직접 교체하는 **direct-main 방식**입니다.  
> 구버전 패치 위에 그대로 덮어쓰기보다 기존 패치 파일을 정리한 뒤 새로 적용하는 것을 권장합니다.

---

## 0. 지원 원본 확인

- Base Title ID: `01008BA00F172000`
- 본편 버전: `v0`
- Update Title ID: `01008BA00F172800`
- 업데이트 버전: `v131072`
- RomForge 표시 버전: `1.02`
- 게임 내 표시 버전: `1.0.2`
- 본편 MD5: `0F262016E3653174090EEA96379E0BE6`
- 업데이트 MD5: `0E605AA5B0C65682A8CBC6136529BCFC`

> [!NOTE]
> RomForge에서는 업데이트가 **1.02**, 게임 안에서는 **1.0.2**로 표시되는 것이 정상입니다.

> [!WARNING]
> **Base만 언팩한 결과는 사용할 수 없습니다.**  
> 반드시 **Base + Update 1.0.2가 함께 반영된 깨끗한 원본**을 사용하세요.

`01008BA00F172800`은 Update Title ID이며, 패처 입력과 실제 모드 폴더에서는 본편 Title ID인 `01008BA00F172000`을 사용합니다.

---

## 1. RomForge로 원본 준비

> [!TIP]
> Base + Update가 함께 반영된 정상 원본이 이미 준비되어 있다면 이 단계는 건너뛰어도 됩니다.

1. RomForge를 실행합니다.
2. 상단 메뉴에서 `Switch` → `리팩` → `파일`로 이동합니다.
3. 본인이 보유한 **EVE rebirth terror Base 파일**과 **Update 1.0.2 파일**을 함께 추가합니다.
4. Output 위치를 지정한 뒤 `언팩`을 실행합니다.
5. 완료 후 아래 구조를 확인합니다.

```text
unpacked
└─ 01008BA00F172000
   ├─ exefs
   │  └─ main
   └─ romfs
      └─ data_eve2
```

패처에서는 아래 둘 중 하나를 선택할 수 있습니다.

- `unpacked` 폴더
- `unpacked` 안의 `01008BA00F172000` 폴더

`romfs` 폴더만 따로 선택하지 마세요.

---

## 2. v1.4.0 패처 실행

1. 배포 ZIP을 원하는 위치에 **완전히 압축 해제**합니다.
2. `EVE-Rebirth-Terror-KR-Patcher.exe`를 실행합니다.
3. 원본 폴더에서 `unpacked` 또는 `01008BA00F172000` 폴더를 선택합니다.
4. 출력 위치를 선택합니다.
5. `한국어 패치 시작`을 누릅니다.
6. 원본 검사 → 패치 적용 → 결과 검사가 끝날 때까지 기다립니다.

패처는 준비한 원본을 직접 수정하지 않고 별도의 결과물을 생성합니다.

**Nintendo Switch 적용에는 아래 결과물을 사용합니다.**

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

---

## 3. Nintendo Switch 적용 방법

> [!CAUTION]
> **기존 Switch 한글패치 위에 그대로 덮어쓰지 마세요.**  
> 구버전 파일이 남아 있으면 새 패치 파일과 충돌할 수 있습니다.

### 방법 A. SD 카드를 PC에 연결해서 설치

1. 실행 중인 `EVE rebirth terror`를 완전히 종료합니다.
2. SD 카드를 분리해서 작업할 경우 Switch 전원을 끈 뒤 SD 카드를 PC에 연결합니다.
3. 아래 기존 모드 폴더가 있다면 **삭제하거나 내부를 완전히 비웁니다.**

```text
SD:/atmosphere/contents/01008BA00F172000
```

4. 패처가 생성한 Switch 결과물 안의 `atmosphere` 폴더를 SD 카드 **최상위 루트**에 복사합니다.
5. 아래 경로가 존재하는지 확인합니다.

```text
SD:/atmosphere/contents/01008BA00F172000/exefs/main
SD:/atmosphere/contents/01008BA00F172000/romfs/data_eve2/...
```

6. SD 카드를 Switch에 다시 넣고 부팅한 뒤 게임을 실행해 한국어 적용 여부를 확인합니다.

### 방법 B. DBI MTP로 SD 카드 분리 없이 설치

1. 실행 중인 `EVE rebirth terror`를 완전히 종료합니다.
2. Switch에서 **DBI**를 실행합니다.
3. **`Run MTP responder`**를 실행합니다.
4. 데이터 전송이 가능한 USB 케이블로 Switch와 PC를 연결합니다.
5. PC 파일 탐색기에서 **`1: SD Card`**를 엽니다.
6. 아래 기존 모드 폴더가 있다면 삭제하거나 내부를 완전히 비웁니다.

```text
1: SD Card/atmosphere/contents/01008BA00F172000
```

7. 패처가 생성한 Switch 결과물 안의 `atmosphere` 폴더를 **`1: SD Card` 최상위 루트**에 복사합니다.
8. 복사가 끝나면 MTP responder를 종료하고 게임을 실행합니다.

> [!TIP]
> 정상적으로 적용되면 별도 재부팅은 필요하지 않습니다.  
> 한글패치가 적용되지 않을 때만 Switch 본체를 재부팅한 뒤 다시 확인해 보세요.

> [!WARNING]
> `01008BA00F172000` 폴더를 SD 카드 루트에 바로 넣는 것이 아닙니다.  
> 반드시 `SD:/atmosphere/contents/01008BA00F172000/` 구조가 되어야 합니다.

---

## 4. 패치가 적용되지 않을 때 확인

1. **게임 버전이 1.0.2인지 확인**
2. RomForge 원본에 **Base + Update가 함께 반영**되어 있는지 확인
3. 다른 한글패치 또는 모드가 섞인 원본을 사용하지 않았는지 확인
4. 기존 `SD:/atmosphere/contents/01008BA00F172000` 폴더를 먼저 정리했는지 확인
5. 게임을 완전히 종료한 뒤 다시 실행하고, 필요할 때만 본체를 재부팅해 확인

패처가 원본 검사 단계에서 중단된다면 **깨끗한 Base + Update 원본부터 다시 준비하는 것을 권장**합니다.

---

## 확인된 호환성

- **Nintendo Switch 실기:** 정상 작동 확인

---

## 주의사항

- 본인이 소유한 게임과 키로 준비한 원본을 사용하세요.
- 패처는 잘못된 Title ID, 버전 또는 수정된 원본을 발견하면 중단할 수 있습니다.
- 배포물에는 원본 게임, 전체 RomFS, 완성된 `main`, NSP/XCI/NCA, `prod.keys`가 포함되지 않습니다.
