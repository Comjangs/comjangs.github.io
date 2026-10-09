<!-- source: 97a83a9d4edb -->
# 빠른 시작

임포트부터 로컬라이즈된 텍스트까지 몇 분이면 됩니다. 단계마다 자세한 설명이 있는 페이지로 연결됩니다.

## 1. 임포트
Seamless Localization을 임포트합니다. Localization 1.5.13 이상이나 Unity UI 2.0.0 이상이 없으면, 임포트가 끝난 뒤 설치를 묻는 창이 뜹니다. **Install**을 누르세요. **Tools > Seamless Localization > Install Required Packages**로 직접 실행할 수도 있습니다. [요구 사항](index.md#requirements)을 참고하세요.

## 2. Set Up
**Tools > Seamless Localization > Settings**를 엽니다.

- **Status** 아래에서 프로젝트에 쓸 언어를 체크합니다. English와 시스템 언어가 미리 선택되어 있습니다.
- **Set Up**을 누릅니다. Localization Settings, 로케일, 폰트 테이블이 `Assets/Localization`에 만들어집니다. 기존 에셋이 있으면 새로 만들지 않고 그것을 씁니다.

[Set Up](settings.md#set-up)을 참고하세요.

## 3. 폰트
**Empty font slots** 줄의 **Fill Default Fonts**를 누릅니다. 빈 칸마다 그 로케일에 맞는 Noto 폰트가 들어가고, 폰트는 `Assets/Localization/Fonts`로 복사됩니다. TMP Essential Resources가 없으면 먼저 가져온 뒤 이어서 채웁니다. 직접 고른 폰트를 쓰려면 **Fonts** 아래 폰트 표에 TextMesh Pro 폰트 에셋을 끌어다 놓으세요.

[Empty font slots](settings.md#empty-font-slots)를 참고하세요.

## 4. 문구
**Window > Asset Management > Localization Tables**를 열어 String Table Collection을 만들고, 키와 로케일별 번역을 입력합니다. 공식 Localization의 작업 방식 그대로입니다. [Localization 빠른 시작 가이드](https://docs.unity3d.com/Packages/com.unity.localization@1.5/manual/QuickStartGuideWithVariants.html)(영어)를 참고하세요. 나중에 **Add Languages**로 언어를 추가하면 문자열 테이블에도 그 언어의 빈 열이 생깁니다.

## 5. 텍스트
- **새 텍스트** — Hierarchy에서 우클릭해 **UI > Text - Localized TMP**를 고른 뒤 **String**을 지정합니다.
- **기존 TextMesh Pro 텍스트** — 컴포넌트 메뉴(⋮)에서 **Localize with Seamless Localization**을 고릅니다.
- **이미 Localize String Event를 쓰는 텍스트** — **Tools > Seamless Localization > Text Converter**를 실행합니다.

텍스트에는 Default Font Role이 자동으로 지정됩니다. `Font.Title`처럼 다른 역할을 쓰려면 인스펙터에서 **Font Role**을 고르세요. [Localized TMP Text](components.md#localized-tmp-text)를 참고하세요.

## 6. 미리보기
씬 뷰의 **Localization Preview** 오버레이로 Edit Mode에서 로케일을 바꿔 봅니다. 텍스트와 폰트가 함께 바뀝니다. Play를 눌러 Play Mode에서도 똑같이 확인하세요. [Localization Preview overlay](components.md#localization-preview-overlay)를 참고하세요.

## 다음 단계
- [데모](demo.md) — 모든 기능을 보여 주는 10개 언어 씬
- [프로젝트 설정](settings.md) — 폰트 역할, 기본 폰트 역할, 미리보기 자리 채움 값
