#   PowerScheduler System

## ⚙ 주요 기능
- 평일 PM 08:00 귀신 사진 열기 AND 스산한 BGM 재생
- 평일 PM 09:00 OS 자동 종료
<br/>

## 🧫 프로젝트 배경
 현대 사회에서 컴퓨터와 기술은 일상 속에서 많은 사람들에게 중요한 역할을 하고 있습니다. 특히 업무 환경이나 집중이 필요한 상황에서는 작업을 마무리하거나 중간중간 휴식과 리프레시가 필요합니다. 이러한 흐름에서, 사람들의 주의를 환기시키고 마감 시간을 알리는 자동화된 시스템을 만들어 보자는 아이디어에서 이번 프로젝트가 시작되었습니다.
<br/>

## 👥 팀원 소개

| 노솔리 | 구동길 | 홍민영 |
|:-----------:|:-----------:|:-----------:|
| <img width="100px" src="https://avatars.githubusercontent.com/soljjang777" /> | <img width="100px" src="https://avatars.githubusercontent.com/dkac0012"/> | <img width="100px" src="https://avatars.githubusercontent.com/u/65701100?v=4"/> |
| [@soljjang777](https://github.com/soljjang777) | [@dkac0012](https://github.com/dkac0012) | [@HongMinYeong](https://github.com/HongMinYeong) |
<br/>

## 🔧 Crontab 작업 예약 가이드
**설치해야 할 패키지**  <br/>
 - alsa-utils: 음악을 재생하는 도구.
 - eog: 이미지를 기본 프로그램으로 여는 명령어.
 ```bash
sudo apt install alsa-utils   # 음악 재생 도구 설치
sudo apt install eog    # 이미지 열기 도구 설치
```
<br/>

**음원과 이미지 위치**  
 ```bash
username@servername:~/project$ tree
.
├── image.png
└── Sound.wav
```
<br/>

**Crontab 명령어**
 ```bash
sudo crontab -e   # 루트 사용자의 crontab 파일을 생성 및 편집
sudo crontab -l   # 루트 사용자의 crontab 파일 내용 표시
```
<br/>

**Crontab 편집**
```crontab
# 평일 오후 8시 귀신 사진 열기와 스산한 BGM 재생
0 20 * * 1-5 DISPLAY=localhost:10.0 eog $HOME/project/image.png
0 20 * * 1-5 aplay  $HOME/project/Sound.wav

# 평일 오후 9시 시스템 자동 종료
0 21 * * 1-5 /sbin/shutdown -h now
```

