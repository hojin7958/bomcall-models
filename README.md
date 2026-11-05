# 봄콜 녹취 검증

삼성 통화녹음 등을 휴대폰 안에서 텍스트로 변환하는 별도 검증 앱과 Whisper Small INT8 모델을 배포합니다.

## 앱 설치

**[봄콜 녹취 검증 0.1.1 APK 다운로드](https://github.com/hojin7958/bomcall-models/releases/download/poc-v0.1.1/bomcall-transcription-poc-0.1.1.apk)** · [변경 내용·체크섬](https://github.com/hojin7958/bomcall-models/releases/tag/poc-v0.1.1)

기존 검증 앱이 있으면 삭제하지 않고 업데이트하세요. 설치된 Small 모델과 마지막 녹취 결과를 유지합니다. 기존 봄콜 앱과는 별도로 설치됩니다.

- Android 11 이상. 패키지: `kr.bomlabs.bomcall.transcription.poc`.
- 디버그 서명된 검증용 APK이며 Play 정식 배포용이 아닙니다.
- 모델 설치 후 기기 내부에서 변환합니다. 원본 녹음과 녹취 내용은 업로드하지 않습니다.
- **변환된 내용 → 전체 복사**로 모든 구간의 본문을 복사합니다. 변환 중에는 현재까지의 내용을 복사합니다.
- 모델 다운로드는 GitHub 우선, Hugging Face 원본을 예비 경로로 사용하며 최대 4개 연결·이어받기·자동 재시도를 지원합니다.

## 모델 설치

앱에서 **모델 다운로드**를 누르세요. Whisper Small INT8 전용이며 파일 합계 약 376 MB, 설치 중 약 800 MB의 여유 공간이 필요합니다. 실행 메모리와 모델 파일 용량은 다릅니다.

PC에서 받아 옮기려면 [모델 릴리스](https://github.com/hojin7958/bomcall-models/releases/tag/whisper-small-int8-v1)의 아래 3개를 **같은 폴더**에 넣고 앱에서 **모델 폴더 가져오기**를 누르세요.

- `small-encoder-attn.int8.onnx`
- `small-decoder-attn.int8.onnx`
- `small-tokens.txt`

원본 모델은 `pantinor/sherpa-onnx-whisper-small`, 고정 리비전 `7d2b7d387617b4aeb3a19534ceb298dc20ff1b34`입니다. 파일을 변경하지 않았습니다. 설치 시 앱에 고정된 크기와 SHA-256으로 확인합니다.

## 출처와 검증 범위

모델 릴리스에 `MODEL-NOTICE.md`, `whisper-LICENSE.txt`, `SHA256SUMS.txt`를 제공합니다. APK에는 제3자 라이선스가 포함되어 있으며 앱 릴리스에서도 확인할 수 있습니다.

기기와 회선에 따라 속도가 다릅니다. 음성인식에는 오류가 있을 수 있으며, 무음 구간에서 없는 문장이 생성된 사례가 있어 원문 확인이 필요합니다. 15·30분 실제 한국어 통화의 품질·발열·배터리 검증은 계속 진행할 예정입니다.
