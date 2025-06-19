# mkdocs 브랜치 문서

이 브랜치는 **파이콘 한국 행동강령 페이지**를 위해 Python으로 이루어진 [MkDocs](https://www.mkdocs.org/)를 사용하며, `mkdocs.yml` 설정 파일과 관련 파일들을 관리합니다.
python 3.11 버전에서 테스트되고 작성되었습니다.

---

## 브랜치 목적

- `mkdocs` 브랜치:
  프로젝트의 문서 소스를 관리합니다.
  MkDocs 설정(`mkdocs.yml`), 문서 마크다운 파일(`docs/` 폴더), 테마, 플러그인 등이 포함됩니다.
- `gh-pages` 브랜치 (참고):
  MkDocs로 빌드한 정적 HTML 파일이 배포되는 브랜치입니다.
  GitHub Pages가 `gh-pages` 브랜치의 내용을 호스팅하여 웹사이트를 제공합니다.

---

## 디렉토리 구조

```plaintext
├── docs/             # 마크다운 형식의 실제 문서들
│   ├── index.md      # 사이트의 홈 페이지
│   └── ...           # 추가 문서들
├── mkdocs.yml        # MkDocs 사이트 설정 파일
├── requirements.txt  # MkDocs 및 관련 플러그인 설치 목록
```

또한 `docs/en`, `docs/ko` 디렉토리를 구분하여 i18n 다국어 지원을 제공합니다.

---

## `mkdocs.yml` 설명

`mkdocs.yml`은 MkDocs의 핵심 설정 파일로, 다음 정보를 포함합니다:

| 설정 항목             | 설명                                                          |
| --------------------- | ------------------------------------------------------------- |
| `site_name`           | 사이트 이름 (문서 웹사이트 제목)                              |
| `nav`                 | 네비게이션 메뉴 구성 (`index.md` 등 문서의 순서 및 구조 설정) |
| `theme`               | 사이트 테마 (예: `material` 테마)                             |
| `plugins`             | MkDocs 플러그인 설정 (검색, 코드 하이라이트 등)               |
| `markdown_extensions` | 추가 마크다운 확장 기능 설정                                  |

| 설정 항목             | 설명                                                                                              |
| --------------------- | ------------------------------------------------------------------------------------------------- |
| `site_name`           | 사이트 이름 (문서 웹사이트 제목)                                                                  |
| `theme`               | 사이트 테마에 대한 설정                                                                           |
| ├─ `name`             | 사용할 테마 이름 (`material`).                                                                    |
| ├─ `logo`             | 사이트 로고 파일 경로.                                                                            |
| ├─ `features`         | 활성화할 추가 UI 기능 (탭, 섹션, 상단 메뉴, TOC 통합, 검색 추천/하이라이트, 코드 주석 등).        |
| ├─ `language`         | 사이트 기본 언어.                                                                                 |
| ├─ `palette`          | 밝은 모드(`default`)와 어두운 모드(`slate`)의 색상 테마 구성.                                     |
| `nav`                 | 네비게이션 메뉴 구성 (`index.md` 등 문서의 순서 및 구조 설정)                                     |
| `extra`               | GitHub, Twitter, Instagram 소셜 아이콘 등의 추가요소를 설정.                                      |
| `markdown_extensions` | Markdown 문법 확장 기능 설정. 코드 하이라이트, 수학, 각주, 아코디언 등의 기능을 활성화할 수 있음. |
| `copyright`           | 사이트 하단에 표시될 저작권 문구.                                                                 |

---

## MkDocs 사용 방법

### 의존성 설치

```bash
pip install -r requirements.txt
```

---

### 로컬 서버 실행

```bash
mkdocs serve
```

- 문서 변경 사항이 자동 반영됩니다.
- 기본 포트는 `8000`입니다.

---

### 로컬에서 문서 사이트 확인

브라우저에서 아래 주소를 열어주세요:

```
http://127.0.0.1:8000/
```

---

## 빌드 및 배포 (참고)

- 문서를 빌드하기전에 로컬에서 제대로 빌드되는지 확인해주세요:

  ```bash
  mkdocs build
  ```

  --> `site/` 폴더에 정적 HTML 파일 생성

- `mkdocs` 브랜치에 commit을 완료하면 Github Action을 통해 `gh-pages` 브랜치에서 배포가 완료됩니다.

---

## 참고 링크

- [MkDocs 공식 문서](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

---

[릴리즈 노트](https://github.com/pythonkr/pycon-code-of-conduct/releases)

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="크리에이티브 커먼즈 라이선스" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />이 저작물은 <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">크리에이티브 커먼즈 저작자표시 4.0 국제 라이선스</a>에 따라 이용할 수 있습니다.
