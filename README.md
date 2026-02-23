# claude-gov-proposal-config

정부과제 제안서 작성을 위한 Claude Code 프로젝트 설정 파일 모음입니다.

## 구조

```
.
├── CLAUDE.md                        # Claude 메인 컨텍스트 및 지시사항
└── .claude/
    ├── settings.local.json          # Claude 권한 설정
    └── agents/
        └── proposal-writer.md      # 정부과제 제안서 작성 서브에이전트 정의
```

## 사용 방법

이 레포의 파일들을 프로젝트 루트 디렉토리에 복사한 후 Claude Code를 실행하면 됩니다.

```bash
cp CLAUDE.md /your-project/
cp -r .claude/ /your-project/
```

## 주요 기능

- **proposal-writer 에이전트**: 정부 R&D 과제 제안서 섹션 작성 전문 서브에이전트
  - 과학기술정보통신부, 산업통상자원부, 중소벤처기업부 등 주요 부처 제안서 형식 지원
  - 그림/다이어그램 삽입 가이드 포함
  - 정량적 목표 및 근거 중심 서술
