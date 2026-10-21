# Presence Studio

[English](README.md) · **한국어**

지금 보는 영상, 듣는 음악, 직접 꾸민 활동을 Discord 활동과 데스크톱·OBS 오버레이에 표시하는 앱입니다.

**Windows 10/11 x64 · Edge / Chrome · YouTube · YouTube Music · SoundCloud · English / 한국어**

이 저장소는 Windows 설치 파일·자동 업데이트·사용 설명서를 제공합니다. 앱과 브라우저 확장 소스는 [presence-studio](https://github.com/LUNA12379/presence-studio)에 공개되어 있습니다.

**[최신 Windows 설치 파일 다운로드](https://github.com/LUNA12379/presence-studio-releases/releases/latest)** · 배포 페이지의 **Assets**에서 `Presence-Studio-<버전>-Setup.exe`를 선택하세요. **2.8.0부터** 설치 파일과 정확히 같은 소스의 `Presence-Studio-<버전>-source.zip`, SHA-256 파일, `release-manifest.json`도 함께 제공합니다. 이 배포 저장소에서 GitHub가 자동으로 표시하는 “Source code”는 안내 문서이므로, 앱 소스는 이름에 `-source.zip`이 붙은 파일을 선택하세요.

## 소스와 라이선스

Presence Studio 2.8.0부터 **GPLv3 전용 라이선스와 좁은 범위의 WebView2 연결·배포 예외**를 적용합니다. [COPYING](https://github.com/LUNA12379/presence-studio/blob/main/COPYING), [LICENSE](https://github.com/LUNA12379/presence-studio/blob/main/LICENSE), [외부 구성요소 고지](https://github.com/LUNA12379/presence-studio/blob/main/THIRD-PARTY-NOTICES.md)를 확인하세요. 빌드와 기여 방법은 [개발 안내](https://github.com/LUNA12379/presence-studio/blob/main/DEVELOPMENT.md)에 있습니다. 이전 설치 파일은 변경하지 않으며 해당 배포에는 새 소스 묶음이 포함되지 않습니다.

## 주요 기능

- 브라우저 확장으로 YouTube·YouTube Music·SoundCloud 재생 감지
- 제목·상태·이미지·링크와 경과 시간·남은 시간으로 직접 활동 꾸미기
- 최대 30개 프리셋 저장, 편집기에서 불러오기 또는 프리셋 메뉴에서 바로 적용
- 사진 자르기, 투명 여백으로 전체 담기, 512 × 512·1024 × 1024 PNG 저장
- 다른 창 위에 띄우는 데스크톱 카드와 투명한 OBS 브라우저 소스
- 재실행해도 유지되는 영어·한국어 선택
- 공개 배포 저장소의 새 버전을 앱에서 확인하고 원하는 때 다운로드·설치

## 설치하고 연결하기

1. [Releases](https://github.com/LUNA12379/presence-studio-releases/releases)에서 `Presence-Studio-<버전>-Setup.exe`를 내려받으세요. Node.js가 포함되며, Microsoft WebView2가 없으면 인터넷으로 설치합니다. .NET Framework 4.7.2 이상이 필요합니다.
2. Presence Studio와 **Discord 데스크톱 앱**을 실행하세요. 앱 상단이나 처음 뜨는 설명서의 **EN / 한국어**에서 언어를 고릅니다. 신규 설치는 영어로 시작하고 기존 설정은 한국어를 유지합니다.
3. [Discord 개발자 페이지](https://discord.com/developers/applications)에서 **New Application**을 눌러 **Discord에 표시하고 싶은 이름**으로 앱을 만드세요. General Information의 **Application ID**를 **연결 & 설정 → 기본 Application ID**에 저장합니다. 비밀번호·사용자 토큰·봇 토큰은 필요 없습니다.
4. **연결 & 설정 → 브라우저 확장 연결**에서 폴더 경로를 복사하세요. Edge의 `edge://extensions` 또는 Chrome의 `chrome://extensions`에서 **개발자 모드 → 압축 풀린 확장 프로그램 로드**로 해당 폴더를 선택합니다. 기존 YouTube·SoundCloud 탭도 새로고침하세요. 사용하는 브라우저마다 확장을 설치하세요. **Edge 확장 관리** 버튼은 Edge를 엽니다. Chrome 사용자는 Chrome 주소창에 `chrome://extensions`를 입력하세요.
5. 영상이나 음악을 재생하세요. 앱의 **활동 공유**를 켜고, Discord의 활동 공유도 꺼져 있다면 켜 주세요.

Microsoft Edge와 Google Chrome을 모두 지원합니다. 설치 파일에 포함된 Chromium Manifest V3 확장을 두 브라우저에서 같은 폴더로 로드하면 됩니다. 연결 상태의 **브라우저 확장**은 두 브라우저 모두에 해당합니다. 현재 브라우저 스토어를 통한 설치는 제공하지 않습니다. [Chrome 공식 압축 풀린 확장 설치 안내](https://developer.chrome.com/docs/extensions/get-started/tutorial/hello-world#load-unpacked)도 참고하세요.

설치 파일에는 아직 코드 서명이 없어 Windows에서 알 수 없는 게시자 경고가 나올 수 있습니다. 프로젝트의 공식 배포 페이지에서 받은 파일을 사용하세요.

Edge와 Chrome 및 여러 브라우저 프로필을 동시에 사용할 수 있습니다. 2.8.0부터 탭을 브라우저별로 구분합니다. 업데이트 후 모든 브라우저에서 확장 **1.2.0**과 미디어 탭을 새로고침하고 예전에 고정한 탭은 다시 선택하세요. 추가된 `storage` 권한은 무작위 프로필 ID를 로컬에 저장하며 동기화하거나 Discord에 보내지 않습니다.

## SoundCloud 사용하기

앱 업데이트 후 `edge://extensions` 또는 `chrome://extensions`에서 **Presence Studio — YouTube & SoundCloud** 확장(이전 이름: **YouTube → Discord 활동**)을 새로고침하세요. 브라우저가 SoundCloud 접근 권한을 요청하면 허용한 뒤 SoundCloud 탭도 새로고침하고 곡을 재생하세요.

하단 재생바에서 곡명·아티스트·커버 이미지·재생 시간·일시정지를 읽습니다. 음악을 재생하면서 다른 SoundCloud 페이지를 둘러봐도 현재 곡을 표시합니다. 자동 활동 종류는 **듣는 중**이며, 사이트를 열 때 복원된 예전 일시정지 곡은 직접 재생하기 전까지 표시하지 않습니다.

여러 탭이 재생 중이면 마지막으로 재생을 시작한 탭이 우선입니다. 일시정지하면 다른 재생 탭으로 전환하며, 대시보드의 **이 탭 고정**으로 고정할 수도 있습니다. 직접 입력 모드를 선택하면 커스텀 활동이 우선합니다. 이번 지원은 브라우저의 SoundCloud 웹사이트이며 별도 PC 앱 감지는 포함하지 않습니다. 비공개 곡 링크는 공유하지 않습니다.

## 활동별 Discord 앱 이름 설정

현재 연결 방식에서는 등록한 애플리케이션 이름이 표시됩니다. **연결 & 설정 → 내 Discord 애플리케이션**에서 ID를 입력하고 **ID 저장 후 연결**을 누르세요.

| 입력칸 | 사용 대상 |
| --- | --- |
| **기본 Application ID** | YouTube, YouTube Music, 전용 ID가 없는 활동 |
| **SoundCloud 전용 Application ID** (선택) | SoundCloud 재생. 표시할 이름을 SoundCloud로 정한 앱의 ID를 저장하세요. |
| **커스텀 활동 전용 Application ID** (선택) | 직접 꾸미기. 예: Presence Studio라는 이름의 앱 |

선택된 미디어 탭이나 커스텀 활동에 맞춰 자동 연결합니다. 전용 ID를 비우면 기본 ID를 사용하므로 같은 이름을 원하면 앱 하나만 만들어도 됩니다. ID는 이 PC에 저장되어 앱·컴퓨터를 다시 켜도 유지됩니다. 봇 토큰이나 서버 초대는 필요 없습니다.

기본 앱 이름이 **YouTube**이면 전용 ID가 없는 SoundCloud와 커스텀 활동도 그 이름으로 표시됩니다. 감지 범위가 바뀌는 것은 아닙니다. 상단 작은 로고는 Discord가 표시하므로 앱 이름을 SoundCloud로 정해도 SoundCloud 로고가 자동으로 붙는 것은 보장하지 않습니다.

## 이미지가 표시되는 두 곳

| 설정 | 표시 위치 |
| --- | --- |
| **내 이미지** | 앱 미리보기·데스크톱·OBS 오버레이. 파일은 이 PC에 보관합니다. |
| **Discord에 표시할 이미지** | 연결한 애플리케이션의 Art Assets에서 고르는 Discord 활동 카드의 큰 사진 |

같은 사진을 쓰려면 **내 이미지**에서 사진을 자르고 보관한 뒤 **PNG로 저장**하세요. **Discord 이미지 등록 → Rich Presence → Art Assets**에 PNG를 올려 저장하고 앱에서 **목록 새로고침**을 누릅니다. PC 사진은 자동 업로드되지 않습니다. 커스텀 전용 ID가 있으면 그 애플리케이션에 등록하세요.

## 오버레이·프리셋·업데이트

- **데스크톱:** **오버레이 → 데스크톱에 표시**를 켜고 카드를 드래그합니다. 위치 잠금과 마우스 클릭 통과를 사용할 수 있습니다.
- **OBS:** 브라우저 소스에 앱이 알려 주는 주소와 크기를 입력합니다. 주소에는 로컬 접근 키가 있으므로 공개하지 마세요. 데스크톱 오버레이가 꺼져 있어도 OBS에는 표시됩니다.
- **프리셋:** **프리셋으로 저장**하면 현재 활동 제목으로 저장합니다. **저장한 프리셋**에서 내용을 불러온 뒤 **이 활동으로 표시하기**로 적용합니다. 불러오기만 해서는 현재 공유 활동이 바뀌지 않습니다.
- **업데이트:** **연결 & 설정 → 앱 업데이트**에서 확인합니다. **앱을 켤 때 새 버전 확인**을 켜면 실행할 때 확인합니다. **새 버전 다운로드 → 설치하고 다시 시작** 순서로 진행하며, 확인만으로 다운로드하거나 설치하지 않습니다. 내려받은 파일의 SHA-256을 배포 정보와 대조한 뒤 설치합니다. 확장 파일이 변경되면 브라우저 확장 관리에서 확장과 YouTube·SoundCloud 탭을 새로고침하세요.
- **단축키:** `Ctrl+Shift+P`는 활동 공유, `Ctrl+Shift+O`는 데스크톱 오버레이를 켜고 끕니다. 창을 닫으면 트레이에 남고 **종료**를 눌러야 완전히 꺼집니다.

Application ID·프리셋·사진·언어 설정은 `%APPDATA%\PresenceStudio`에 저장합니다. 업데이트·PC 재부팅 후에도 유지되며 앱을 제거해도 이 폴더는 남아 다시 설치할 때 사용할 수 있습니다.

배포처가 연결되지 않은 초기 버전은 최신 Setup.exe를 한 번 설치하세요. 이후 버전은 앱에서 설치할 수 있습니다. 기존 설정은 유지됩니다.

## 개인정보와 도움말

확장은 현재 재생 정보를 PC 안의 로컬 연결 프로그램에 보내고, 앱은 선택한 활동을 Discord 데스크톱 클라이언트에 전달합니다. 시청 기록 데이터베이스는 만들지 않습니다. 제외 키워드와 일시정지 숨기기를 설정할 수 있으며 Discord 자체 개인정보 설정도 적용됩니다. 외부 이미지 주소를 넣으면 앱이나 Discord에서 해당 이미지를 불러올 수 있습니다.

**연결 & 설정 → 설명서 보기**에서 설명서를 다시 열 수 있습니다. 이미지 목록이 비었다면 앱에 저장한 ID와 사진을 올린 애플리케이션이 같은지 확인하고, 개발자 페이지에서 저장한 뒤 새로고침하세요.

일반 문제는 [소스 Issues](https://github.com/LUNA12379/presence-studio/issues)에 앱 버전과 재현 순서를 적어 주세요. `config.json`, 생성된 `connection.js`, 개인 오버레이 주소나 개인정보가 담긴 화면은 그대로 첨부하지 마세요.

보안 문제는 [비공개 취약점 신고](https://github.com/LUNA12379/presence-studio/security/advisories/new)를 이용하고, 자격 증명이나 악용 방법은 공개 이슈에 올리지 마세요.

Presence Studio는 Discord·Google·YouTube·SoundCloud·Microsoft와 제휴하지 않은 독립 프로젝트입니다.
