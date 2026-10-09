<!-- source: 319427c417e2 -->
# 데모

데모는 10개 언어(영어, 독일어, 스페인어, 프랑스어, 브라질 포르투갈어, 러시아어, 일본어, 한국어, 중국어 간체, 중국어 번체)로 Seamless Localization을 보여 줍니다. 데모 전용 테이블과 폰트만 쓰므로, 여러분의 테이블과 폰트는 바뀌지 않습니다.

## 데모 가져오기
**Tools > Seamless Localization > Import Demo**를 고르고 **Import**를 누르세요. Unity 6.6 이상에서는 가져오기 창에 패키지 서명이 없다는 경고와 **Import Anyway** 버튼이 나옵니다. 여러분이 속한 조직이 서명하지 않은 패키지에는 모두 나오는 안내이므로 **Import Anyway**를 누르면 됩니다. 데모는 Seamless Localization 폴더 안의 **Samples** 폴더에 들어갑니다. 프로젝트에 없는 데모 언어는 Localization 패키지가 그 폴더 안에 로케일로 추가합니다. 이 로케일은 설정 페이지에서 데모 폰트 테이블(SL Demo Fonts)을 골랐을 때만 나오며, 거기서 여러분의 폰트로 바꿔 시험해 볼 수도 있습니다. 데모는 Seamless Localization에 포함된 Noto 폰트를 쓰며, Play에서 불러올 수 있도록 임포트가 끝나면 Addressables에 자동으로 등록됩니다.

## 써 보기
- Samples 폴더의 **Demo** 씬을 엽니다.
- Play를 누르고 아래쪽 버튼으로 언어를 바꾸거나, 씬 뷰의 **Localization Preview** 오버레이를 쓰세요.

## 데모 제거
데모를 다 본 뒤에는 **Tools > Seamless Localization > Remove Demo**를 고르세요(**Demo Info**의 **Remove Demo** 버튼도 같습니다). 할 일을 먼저 보여 주고 확인을 받습니다. 데모 씬이 열려 있으면 닫고, 데모 언어(데모 폴더 안의 로케일)를 제거하고, Project Settings의 폰트 테이블이 데모 폰트 테이블을 가리키면 Fonts로 되돌린 뒤, Samples 폴더를 지우고, 비게 된 Localization Addressables 그룹을 정리합니다. 로케일은 프로젝트 전체 설정이라, 그대로 두면 추가된 로케일이 게임에 남습니다. 시스템 언어가 그중 하나인 플레이어는 번역이 없는 언어로 게임을 시작할 수 있습니다. 여러분의 로케일·테이블·폰트는 바뀌지 않습니다. **Import Demo**로 데모를 다시 가져올 수 있습니다.

## 보여 주는 것
- **왼쪽과 오른쪽** — 같은 문구를 왼쪽은 공식 Localize String Event로, 오른쪽은 Localized TMP Text로 보여 줍니다. 왼쪽은 폰트가 바뀌지 않아 일본어·한국어·중국어가 깨지고, 오른쪽은 폰트가 로케일을 따라 바뀝니다. 왼쪽 텍스트의 빠진 글자마다 TextMesh Pro가 콘솔에 경고를 남기는데, 이는 정상입니다.
- **제목과 본문** — 제목은 Font.Title 역할, 본문은 Font.Body 역할을 쓰며, 로케일마다 각자의 폰트가 적용됩니다.
- **카운터** — **Add item**을 누르면 코드에서 `SetArguments`로 Smart String 인자를 바꿉니다.
- **드롭다운** — 패널 아래 왼쪽의 TextMesh Pro 드롭다운은 영어 옵션 그대로입니다. Localization 패키지에는 드롭다운 옵션용 컴포넌트가 없기 때문입니다. 오른쪽 Localized TMP Dropdown은 로케일에 맞춰 옵션과 폰트를 바꾸고 선택한 옵션을 유지합니다.

## 폰트
데모는 SIL Open Font License의 Noto Sans, Noto Sans JP, Noto Sans KR, Noto Sans SC, Noto Sans TC(Regular, Bold)를 씁니다. Seamless Localization 폴더의 **Third-Party Notices.txt**를 참고하세요. 이 폰트들은 해당 라이선스에 따라 여러분의 프로젝트에서도 쓸 수 있습니다.
