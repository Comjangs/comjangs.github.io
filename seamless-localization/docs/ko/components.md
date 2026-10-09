<!-- source: 94c99fc31931 -->
# 컴포넌트

## Localized TMP Text
TextMesh Pro 텍스트에 로컬라이즈된 문구를 표시하고, 로케일에 맞춰 폰트를 바꿉니다. 문구와 폰트는 따로 불러오지만 둘 다 그 로케일로 준비됐을 때 함께 적용하므로, 글자가 깨진 채 깜빡이는 순간이 생기지 않습니다.

추가하는 방법은 다음과 같습니다.
- **새 텍스트** — Hierarchy에서 우클릭하고 **UI > Text - Localized TMP**를 고릅니다.
- **새 버튼·인풋필드** — **UI > Button - Localized TMP** 또는 **UI > Input Field - Localized TMP**를 고릅니다. 버튼 라벨과 인풋필드의 Placeholder에는 Localized Text가 붙습니다. 인풋필드의 입력 텍스트에는 Font Only가 붙습니다. 인풋필드가 직접 채우는 텍스트이기 때문입니다.
- **새 드롭다운** — **UI > Dropdown - Localized TMP**를 고릅니다. 옵션과 Caption·항목의 폰트를 맡는 **Localized TMP Dropdown**(아래)이 붙습니다.
- **기존 텍스트** — TextMesh Pro 컴포넌트의 메뉴(⋮)를 열고 **Localize with Seamless Localization**을 고릅니다.
- **Add Component > Seamless Localization > Localized TMP Text**.
- **이미 Localize String Event를 쓰는 텍스트** — [텍스트 변환기](text-converter.md)를 쓰세요.

Default Font Role이 자동으로 지정됩니다.

- **Mode** — Localized Text는 문구와 폰트를 함께 바꾸고, Font Only는 폰트만 바꿉니다. 플레이어 이름처럼 코드가 넣는 텍스트에는 Font Only를 쓰세요.
- **String** — 표시할 로컬라이즈 문구입니다.
- **Font Table** — 이 텍스트가 폰트를 가져오는 Asset Table Collection입니다. 새 컴포넌트에는 [프로젝트 설정](settings.md#fonts)의 Font Table이 들어갑니다. 데모의 SL Demo Fonts처럼 다른 테이블을 쓰면 정보 아이콘이 표시됩니다.
- **Font Role** — 현재 로케일에서 적용할 폰트의 역할로, Font Table의 키입니다. 새 컴포넌트에는 [프로젝트 설정](settings.md#fonts)의 Default Font Role이 들어갑니다. 폰트 역할을 바꿔도 Font Table은 그대로 유지됩니다.
- **Preview Arguments** — 에디터 미리보기에서만 쓰는 Smart String 인자입니다. 비어 있으면 모든 인자 자리에 [프로젝트 설정](settings.md#preview)의 Placeholder Argument가 들어갑니다. `3`처럼 숫자로 읽히는 값은 숫자로 넘어가므로, 미리보기에서도 복수형(plural)이 동작합니다. 인자가 Smart String에 맞지 않으면 미리보기는 이전 문구를 유지하고 그 텍스트에 대해 경고를 한 번 남깁니다.

에디터 모드에서는 선택한 로케일의 문구와 폰트로 미리 보여 줍니다. 미리보기 값은 씬에 저장되지 않습니다.

### Localization Preview 오버레이
씬 뷰의 **Localization Preview** 오버레이로 모든 Localized TMP Text의 미리보기 로케일을 한 번에 바꿀 수 있습니다. 목록에서 로케일을 고르거나, ◀ ▶로 로케일을 차례로 넘기며 언어별 화면을 확인하세요. 에디터 모드와 Play 모드 모두에서 동작하며, Localization Scene Controls 창과 같은 로케일 값을 바꿉니다.

다른 오버레이처럼 옮기거나, 씬 뷰 툴바에 붙이거나, 아이콘으로 접을 수 있습니다. 접으려면 제목줄을 우클릭하고 **Collapse**를 고르세요. 보이거나 숨기려면 씬 뷰의 Overlays 메뉴를 여세요(씬 뷰에서 ` 키).

폰트 테이블에 현재 로케일의 폰트가 없으면, 텍스트는 지금 폰트를 그대로 쓰고 에디터에 경고가 기록됩니다.

### 스크립트
| 멤버 | 설명 |
|---|---|
| `SetKey(string key)` | 같은 테이블에서 이 키의 항목을 표시합니다. |
| `SetEntry(TableEntryReference entry)` | 같은 테이블에서 이 항목(키 또는 ID)을 표시합니다. |
| `SetArguments(params object[] args)` | Smart String 인자를 넣고 텍스트를 갱신합니다. 포맷 오류를 피하려면 오브젝트를 활성화하기 전에 호출하세요. |
| `Text` | 컴포넌트가 쓰는 `LocalizedString`입니다. |
| `Font` | 컴포넌트가 쓰는 `LocalizedTmpFont`입니다. |
| `Mode` | 현재 모드입니다. |

## Localized TMP Dropdown
TextMesh Pro 드롭다운에 로컬라이즈된 옵션을 표시하고, Caption과 항목의 폰트를 로케일에 맞춰 바꿉니다. 옵션과 폰트가 모두 그 로케일로 준비된 뒤 한꺼번에 적용하므로, 옵션 글자가 깨진 채 깜빡이지 않습니다. 선택한 옵션은 그대로 유지됩니다.

**UI > Dropdown - Localized TMP**로 만들거나, 기존 TextMesh Pro 드롭다운에 **Add Component > Seamless Localization > Localized TMP Dropdown**을 추가합니다. Default Font Role이 자동으로 지정됩니다.

- **Options** — 옵션마다의 로컬라이즈 문구와 이미지(선택)입니다. Play 모드에서는 이 옵션이 TMP Dropdown의 옵션을 대신합니다. 목록이 비어 있으면 드롭다운의 원래 옵션을 그대로 두고 폰트만 바꿉니다.
- **Font Table**, **Font Role** — 위의 Localized TMP Text와 같습니다. 폰트는 Caption과 항목 틀에 적용됩니다.

목록이 펼쳐진 상태에서 로케일이 바뀌면 목록이 닫히고, 다시 펼치면 새 옵션이 나옵니다. 옵션을 바꾸면 씬이 수정되기 때문에 에디터 모드 미리보기는 없습니다.

### 스크립트
| 멤버 | 설명 |
|---|---|
| `SetOptions(params LocalizedString[] texts)` | 옵션을 바꿉니다. |
| `SetOptions(TableReference table, params string[] keys)` | 한 테이블의 이 키들로 옵션을 바꿉니다. |
| `Options` | 현재 옵션입니다. |
| `Font` | 컴포넌트가 쓰는 `LocalizedTmpFont`입니다. |

선택한 옵션을 읽거나 바꿀 때는 TMP Dropdown의 `value`를 쓰세요.
