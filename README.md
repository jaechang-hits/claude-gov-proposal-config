# claude-gov-proposal-config

정부과제 제안서 작성을 위한 Claude Code 프로젝트 설정 파일 모음입니다.

## 구조

```
.
├── CLAUDE.md                             # Claude 메인 컨텍스트 및 지시사항
└── .claude/
    ├── settings.local.json               # Claude 권한 설정
    ├── agents/
    │   ├── proposal-writer.md            # 정부과제 제안서 작성 서브에이전트
    │   ├── pptx-creator.md              # PowerPoint 생성/편집 서브에이전트
    │   └── researcher.md                # 웹+학술 DB 조사 서브에이전트
    └── skills/
        ├── pptx/                         # PPT 생성/편집 스킬
        │   ├── SKILL.md
        │   ├── editing.md               # 기존 PPT 편집 워크플로우
        │   ├── pptxgenjs.md             # PptxGenJS 기반 생성 가이드
        │   └── scripts/                 # unpack/pack/validate 스크립트
        └── frontend-design/
            └── SKILL.md                 # 프론트엔드 디자인 원칙
```

## 사용 방법

이 레포를 클론한 후, 파일들을 프로젝트 루트 디렉토리에 복사하면 됩니다.

```bash
git clone https://github.com/jaechang-hits/claude-gov-proposal-config.git
cp claude-gov-proposal-config/CLAUDE.md /your-project/
cp -r claude-gov-proposal-config/.claude/ /your-project/
cp claude-gov-proposal-config/pixi.toml /your-project/
```

### 환경 셋업 (pixi)

Python/Node 환경은 [pixi](https://pixi.sh)로 관리합니다.

```bash
# pixi 설치 (최초 1회)
curl -fsSL https://pixi.sh/install.sh | bash

# 의존성 설치
pixi install

# NPM 패키지 셋업 (PptxGenJS 등)
pixi run setup
```

> **Python 실행 규칙**: 모든 Python 스크립트는 `pixi run python`으로 실행합니다. (`python` 직접 호출 금지)

## 서브에이전트

| 에이전트 | 역할 |
|----------|------|
| `proposal-writer` | 정부 R&D 과제 제안서 섹션 작성 전문. 과기부·산업부·중기부 등 주요 부처 형식 지원 |
| `pptx-creator` | PowerPoint 파일 생성 및 편집 전문. PptxGenJS 또는 unpack/edit/pack 워크플로우 |
| `researcher` | 웹 및 학술 DB 조사 전문. 기술 트렌드·시장 규모·정책 자료 리서치 |

## 스킬

| 스킬 | 역할 |
|------|------|
| `pptx` | PPT 생성/편집 방법론 (PptxGenJS, python-pptx, unpack/pack 스크립트 포함) |
| `frontend-design` | 프로덕션 수준 프론트엔드 디자인 원칙 |
