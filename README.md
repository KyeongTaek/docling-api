# Documents to Markdown Converter Server
> PDF, DOCX, PPTX, CSV, HTML, JPG, PNG, TIFF, BMP, AsciiDoc, and Markdown 등의 파일을 Markdown으로 바꿔주는 [Docling](https://github.com/docling-project/docling)에 대한 API를 제공하는 백엔드 서버입니다

## Goal
docling 패키지가 지원하는 확장자 중, xlsx가 빠져 이를 추가하고자 합니다

## Requirements
- `python`==`3.8`
- `poetry`
- `redis server`==`5.2.0`

## How to install & Run
### Docker container 생성 및 실행
CPU만 사용해 서비스를 이용하는 방법입니다
```
docker compose -f docker-compose.cpu.yml up --build --scale celery_worker=1
```
`ip:port/docs`에서 API 서버가 대기합니다. 접속하여, convert_document에 엑셀 파일을 넣고 실행을 누르면 json 양식으로 변환된 내용이 나옵니다

### 디렉토리 구조
- docling-api
  - document_converter
    - route.py
    - service.py
    - schema.py
    - utils.py
  - Dockerfile
  - docker-compose.cpu.yml
  - pyproject.toml
  - .env
  - main.py
  - README.md

### 실행을 종료하는 방법
`ctrl + c`를 이용하여 실행을 종료할 수 있습니다

### License
LICENSE 탭에서 더 자세한 내용을 볼 수 있습니다