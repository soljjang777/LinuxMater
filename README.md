#   PowerScheduler System

## ⚙ 작업 내용
- 평일 PM 08:00 귀신 사진 열기 AND 스산한 BGM 재생
- 평일 PM 09:00 OS 자동 종료
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

**Crontab 명령어**
 ```bash
sudo crontab -e   # 루트 사용자의 crontab 파일을 생성 및 편집
sudo crontab -l   # 루트 사용자의 crontab 파일 내용 표시
```
<br/>

**Crontab 편집**
```crontab
# 평일 오후 8시 귀신 사진 열기와 스산한 BGM 재생
0 20 * * 1-5 DISPLAY=localhost:10.0 eog $HOME/image.png 
0 20 * * 1-5 aplay $HOME/Sound.wav

# 평일 오후 9시 시스템 자동 종료
0 21 * * 1-5 /sbin/shutdown -h now
```

