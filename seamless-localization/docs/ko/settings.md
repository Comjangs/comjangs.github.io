<!-- source: c4ce5deb246d -->
# 프로젝트 설정

**Tools > Seamless Localization > Settings** 또는 **Edit > Project Settings > Seamless Localization**을 엽니다. 모든 설정은 이 페이지 한 곳에 있고 `ProjectSettings/SeamlessLocalizationSettings.asset`에 저장되므로, 버전 관리로 팀과 공유됩니다.

## Reset to Defaults
페이지 오른쪽 위 메뉴(⋮)에서 **Reset to Defaults**를 고르면 Seamless Localization 설정이 모두 기본값으로 돌아갑니다. Localization 에셋, 테이블, 폰트는 바뀌지 않습니다.

Seamless Localization을 제거해도 설정 파일은 `ProjectSettings`에 남습니다. 나중에 다시 설치하면 이전 설정을 보여 주고 유지할지 초기화할지 묻습니다. 새 버전으로 업데이트할 때는 묻지 않습니다.

## Status
프로젝트가 준비됐는지 점검합니다. 실패한 항목마다 도움말 버튼이 있고, 가능한 경우 바로 해결하는 버튼이 함께 나옵니다.

### Set Up
Localization Settings, 로케일, 폰트 테이블 중 하나라도 없으면 나타납니다. **Set Up**을 누르면 한 번에 준비됩니다. 실제로 바꾸기 전에 무엇을 할지 대화 상자로 먼저 보여 줍니다.

- 빠진 항목만 처리합니다. 기존 에셋이 있으면 새로 만들지 않고 그것을 씁니다. 기존 Localization Settings 에셋은 활성으로 지정하고, 기존 로케일은 등록합니다.
- 새 에셋은 `Assets/Localization`에 만들어집니다.
- 프로젝트에 로케일이 없으면 버튼 위 체크박스에서 언어를 고릅니다. 목록은 English, German, Spanish, French, Portuguese (Brazil), Russian, Japanese, Korean, Chinese (Simplified), Chinese (Traditional)이고, 시스템 언어가 목록에 없으면 함께 나옵니다. English와 시스템 언어가 미리 선택되어 있습니다. 나중에 더 추가하려면 [Add Languages](#add-languages)를 쓰세요.

폴더와 로케일을 직접 고르려면 아래 각 항목의 버튼을 쓰세요.

### Add Languages
셋업이 끝나면 로케일 줄에 **Add Languages** 버튼이 생깁니다. 누르면 같은 언어 체크박스가 나오고, 이미 프로젝트에 있는 언어는 체크된 채 잠겨 있습니다. 추가할 언어를 체크하고 **Add**를 누르세요.

- 새 로케일은 기존 로케일이 있는 폴더에 만들어지고, 폰트 테이블과 문자열 테이블에도 그 로케일의 테이블이 추가됩니다(문자열 테이블은 빈 상태로 — 바로 번역을 입력할 수 있습니다). 기존 번역은 바뀌지 않습니다.
- 이어서 새로 생긴 빈 칸에 **Fill Default Fonts**를 실행할지 묻습니다.
- 목록에 없는 언어는 **Project Settings > Localization**의 **Locale Generator**를 쓰세요.
- **Remove Languages**로 뺀 뒤 남아 있는 로케일 에셋은 같은 언어를 다시 추가할 때 재사용됩니다.

### Remove Languages
로케일이 두 개 이상이면 로케일 줄에 **Remove Languages** 버튼도 나옵니다. 뺄 언어를 체크하고 **Remove**를 누르세요. 언어는 하나 이상 남아 있어야 합니다.

- 로케일이 프로젝트 언어 목록에서 빠지고, 폰트 테이블에서도 그 언어의 테이블이 제거됩니다.
- 번역(문자열 테이블)과 로케일 에셋은 남기므로, 같은 언어를 다시 추가하면 그대로 돌아옵니다.
- 데모와 함께 추가된 로케일은 목록에 나오지 않습니다. **Remove Demo**가 지웁니다.

### Localization Settings missing
Localization 패키지의 설정 에셋이 없습니다. **Open Localization**을 눌러 Localization 설정 페이지에서 만드세요.

### No locales
로케일이 하나도 없습니다. **Open Localization**을 누르고 **Add Locale** 또는 **Add All**로 로케일을 추가하세요.

### TMP Essential Resources missing
TextMesh Pro 설정과 셰이더를 아직 프로젝트로 가져오지 않았습니다. **Import**를 누르세요. Fill Default Fonts도 이것이 없으면 먼저 가져온 뒤 이어서 진행합니다.

### Font table missing
**Fonts**에 지정한 폰트 테이블이 없습니다. **Create**를 누르고 `Assets` 안의 폴더를 고르세요. 로케일마다 테이블이 하나씩 함께 만들어집니다.

### Empty font slots
폰트가 지정되지 않은 칸이 있습니다. 아래 **Fonts**의 폰트 표에서 채우거나 **Fill Default Fonts**를 누르세요.

**Fill Default Fonts**는 빈 칸만 Seamless Localization에 포함된 Noto 폰트로 채웁니다. 이미 폰트가 있는 칸과, 폰트 테이블에 아직 테이블이 없는 로케일은 건너뜁니다. 그런 로케일은 먼저 **Add Table**로 테이블을 추가하세요. 실제로 바꾸기 전에 칸마다 들어갈 폰트를 대화 상자로 보여 줍니다.

- 로케일에 필요한 폰트만 `Assets/Localization/Fonts`로 복사하고, Dynamic TextMesh Pro 폰트 에셋과 폰트 라이선스도 함께 만듭니다. 이미 복사해 둔 폰트가 있으면 그것을 씁니다.
- 일본어·한국어·중국어 간체·중국어 번체는 Noto Sans JP·KR·SC·TC를 씁니다. 라틴·그리스·키릴 문자를 쓰는 언어는 Noto Sans를 씁니다. 아랍어·태국어 같은 그 밖의 로케일은 건너뛰니 폰트를 직접 지정하세요.
- 이름에 Title, Bold, Head가 들어간 폰트 역할은 Bold 폰트를, 나머지는 Regular 폰트를 받습니다.

### Fonts not in Addressables
폰트 테이블의 일부 폰트가 Addressables에 등록되어 있지 않아 Play에서 불러올 수 없고, 그 폰트를 쓰는 텍스트가 바뀌지 않습니다. 폰트 테이블을 패키지나 병합으로 가져왔을 때 생깁니다. Localization 패키지는 테이블은 등록하지만 테이블이 쓰는 폰트는 등록하지 않습니다. **Register**를 누르면 등록됩니다.

## Fonts
로케일마다, 폰트 역할마다 어떤 TextMesh Pro 폰트 에셋을 쓸지 정합니다.

- **Font Table** — 폰트를 담는 Asset Table Collection입니다. 이름을 입력하거나 **Select**로 기존 테이블을 고르세요. 새 텍스트는 이 테이블을 씁니다. 텍스트마다 인스펙터의 **Font Table**에서 다른 테이블을 고를 수도 있습니다.
- **Keep Dynamic Fonts Clean** — 폰트 테이블의 Dynamic 폰트가 텍스트를 보여 주면서(에디터·Play) 추가하는 글자 데이터를 디스크에 저장하지 않습니다. 그래서 버전 관리에서 폰트 파일이 바뀌지 않습니다. 필요할 때 원본 폰트에서 다시 만들어집니다. 폴백 목록처럼 직접 바꾼 폰트 설정은 그대로 저장됩니다. 기본으로 켜져 있습니다.
- **Font Roles** — 프로젝트에서 쓰는 폰트 역할입니다(예: `Font.Body`, `Font.Title`). 폰트 역할은 각각 폰트 테이블의 키가 됩니다. 목록에서 역할을 지워도 테이블에 지정된 폰트는 지워지지 않습니다.
- **Default Font Role** — 새로 추가하는 텍스트 컴포넌트에 자동으로 지정되는 폰트 역할입니다.

### 폰트 표
행은 선택한 폰트 테이블에 테이블이 있는 로케일과, 아직 테이블이 없는 여러분의 로케일(**Add Table** 표시)입니다. 데모와 함께 Seamless Localization 폴더 안에 추가된 로케일은 데모 폰트 테이블에서만 **(demo)** 표시와 함께 나오고, Status의 로케일 줄에 따로 표시됩니다.

- 칸에 폰트 에셋을 끌어다 놓으면 지정되고, 칸을 비우면 지정이 해제됩니다. Undo를 지원합니다.
- **Fill Empty** — 이 행에 폰트를 놓으면 그 열의 빈 칸 전체에 지정됩니다.
- **Add Table** — 이 로케일에 빠진 테이블을 추가합니다. 폰트 테이블을 만든 뒤에 로케일을 추가했을 때 나타납니다.

## Preview
[Localized TMP Text](components.md#localized-tmp-text)의 에디터 미리보기를 설정합니다.

- **Placeholder Argument** — 컴포넌트에 Preview Arguments가 없을 때, 에디터 미리보기에서 모든 Smart String 인자 자리에 들어가는 값입니다. 복수형(plural)처럼 숫자가 필요한 포매터에는 0으로 읽혀, 오류 대신 예를 들어 `- items`처럼 보입니다.
