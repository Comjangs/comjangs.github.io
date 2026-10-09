<!-- source: 7369a9dd86f0 -->
# 텍스트 변환기

이미 공식 **Localize String Event**로 프로젝트를 로컬라이즈하셨나요? 텍스트 변환기는 그 텍스트들을 몇 번의 클릭으로 **Localized TMP Text**로 바꿉니다. 그러면 폰트가 로케일을 따라 바뀌어 CJK 문구가 더 이상 깨지지 않습니다. 테이블과 키는 그대로이고, 변환은 언제든 되돌릴 수 있습니다.

## 빠른 시작
- **먼저 프로젝트를 버전 관리에 커밋하세요.** 프리팹 변경은 Undo로 되돌릴 수 없습니다.
- **Edit > Project Settings > Seamless Localization**을 엽니다. 열린 씬에 Localize String Event를 쓰는 텍스트가 있으면 Status 목록에 그 개수가 나옵니다. 거기서 **Convert**를 누르거나, **Tools > Seamless Localization > Text Converter**를 여세요.
- 변환기가 열린 씬과 모든 프리팹을 스캔한 뒤, 바꿀 수 있는 텍스트를 **Ready to convert**에 보여 줍니다. 그대로 두고 싶은 텍스트는 체크를 해제하세요.
- **Convert**를 누릅니다. 완료 화면에 변환된 개수가 나오고, 씬 변경은 그 자리에서 되돌릴 수 있습니다.

텍스트 하나만 바꾸려면 그 텍스트의 Localize String Event 컴포넌트 메뉴(⋮)에서 **Convert to Localized TMP Text**를 고르세요.

## 바뀌는 것
| 변환 전 | 변환 후 |
|---|---|
| TextMesh Pro 텍스트 + Localize String Event | TextMesh Pro 텍스트 + Localized TMP Text |
| 이벤트의 문구 참조와 Smart String 지역 변수 | Localized TMP Text에 같은 문구 참조와 지역 변수 |
| TextMesh Pro 텍스트에 지정된 폰트 | 폰트 테이블에서 Default Font Role의 폰트(Options에서 변경 가능) |

프리팹 인스턴스 안의 텍스트는 원본 프리팹 에셋을 통해 변환되므로, 그 프리팹을 쓰는 모든 씬에 반영됩니다. 열려 있지 않은 씬은 스캔하지 않습니다. 그 씬을 열고 다시 스캔하세요. 데모의 비교용 텍스트처럼 Seamless Localization 폴더 안의 씬·프리팹은 변환하지 않습니다.

## Needs your attention
안전하게 바꿀 수 없는 텍스트는 이유와 할 일이 함께 표시됩니다. **Select**로 해당 오브젝트를 찾을 수 있습니다.

| 이유 | 할 일 |
|---|---|
| The Localize String Event has no listener | 이 텍스트를 바꾸는 것이 없습니다. 필요 없다면 Localize String Event를 지우거나, Localized TMP Text를 직접 추가하세요. |
| The Localize String Event has other listeners | 다른 리스너를 다른 곳으로 옮긴 뒤, Localize String Event 메뉴(⋮)에서 변환하세요. |
| The Localize String Event sets something other than this text | 이 이벤트는 다른 오브젝트나 속성을 바꿉니다. 그대로 두거나 직접 변환하세요. |

## Options
- **Include Plain Texts** — Localize String Event가 없는 TextMesh Pro 텍스트(코드가 넣는 플레이어 이름, 숫자 등)에도 Font Only 모드로 Localized TMP Text를 추가합니다. 그러면 그 텍스트의 폰트도 로케일을 따라 바뀝니다.
- **Font Role** — 변환한 텍스트에 지정할 폰트 역할입니다. 바꾸지 않으면 Default Font Role을 씁니다.

## 되돌리기
- **변환 직후** — 완료 화면의 **Undo scene changes**를 누르거나 Undo를 쓰세요. 열린 씬의 텍스트가 되돌아갑니다.
- **나중에, 또는 프리팹에서** — Localized TMP Text 컴포넌트 메뉴(⋮)에서 **Revert to Localize String Event**를 고르세요. 같은 문구 참조와 텍스트를 바꾸는 리스너를 가진 Localize String Event가 다시 만들어지고, Localized TMP Text는 지워집니다. 폰트는 TextMesh Pro 컴포넌트에 저장된 원래 폰트로 돌아갑니다. Font Only 모드의 텍스트는 Localized TMP Text만 지워집니다.
