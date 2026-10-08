# RemoteDesk 다운로드

macOS ↔ Windows 원격 데스크톱. 화면 보기, 마우스/키보드 제어, **복사·붙여넣기(텍스트·이미지·파일)** 양방향 공유.

## ⬇️ 다운로드 → [최신 버전 받기](https://github.com/sanghakbae/remotedesk-download/releases/latest)

| 컴퓨터 | 파일 |
|---|---|
| Windows 10/11 (설치형, 권장) | `RemoteDesk-x.y.z-Windows-Setup.exe` |
| Windows (설치 없이 실행) | `RemoteDesk-x.y.z-Windows-portable.zip` → 압축 풀고 `RemoteDesk.exe` |
| Mac (Apple Silicon: M1~M4) | `RemoteDesk-x.y.z-macOS-arm64.dmg` |
| Mac (Intel) | `RemoteDesk-x.y.z-macOS-x86_64.dmg` |

## 사용법

**제어받을 컴퓨터**와 **제어할 컴퓨터** 양쪽에 설치합니다.

1. 제어받을 컴퓨터: RemoteDesk 실행 → **공유 시작** → 접속 비밀번호 설정.
   창에 표시되는 **이 컴퓨터 주소**(예: 192.168.0.10)를 확인합니다.
2. 제어할 컴퓨터: RemoteDesk 실행 → **원격 컴퓨터에 연결...** → 주소와 비밀번호 입력.

### Windows 처음 실행 시
- "Windows의 PC 보호" 창이 뜨면 **추가 정보 → 실행**을 누르세요 (서명되지 않은 프로그램이라 표시됩니다).
- 공유를 시작하면 방화벽 설정을 위해 **"디바이스를 변경하도록 허용"** 창이 한 번 뜹니다 → **예**.
- 작업 관리자처럼 관리자 권한 창까지 제어하려면 RemoteDesk를 **관리자 권한으로 실행**하세요.

### Mac 처음 실행 시
- DMG를 열고 RemoteDesk를 **응용 프로그램** 폴더로 끌어다 놓은 뒤 실행하세요.
- "Apple에서 확인할 수 없습니다" → **시스템 설정 › 개인정보 보호 및 보안 › 그래도 열기**.
- 공유(제어받기)하려면 창에 표시되는 **화면 기록**, **손쉬운 사용** 권한을 허용하고 앱을 다시 실행하세요.
- 연결할 때 **로컬 네트워크** 접근을 물으면 **허용**.

## 키보드
- Mac에서 Windows 제어: `Cmd` = `Ctrl` (Cmd+C/V 그대로), **오른쪽 Cmd = 한/영**
- Windows에서 Mac 제어: `Ctrl` = `Cmd`
- 한글은 원격 컴퓨터의 한/영 전환으로 입력합니다.
- Win 키, Alt+Tab 등은 뷰어 툴바의 **특수 키** 메뉴를 사용하세요.

## 연결이 안 될 때
- 양쪽이 **같은 네트워크**에 있는지 확인하세요. (다른 네트워크라면 Tailscale 같은 VPN 권장)
- 제어받을 컴퓨터에서 **공유 시작** 상태인지, 방화벽/백신이 TCP **47800** 포트를 허용하는지 확인하세요.
- 로그: `사용자 폴더/.remotedesk/logs/`

## 보안
비밀번호는 전송되지 않으며(scrypt + 상호 인증), 모든 통신은 AES-256-GCM으로 암호화됩니다.
