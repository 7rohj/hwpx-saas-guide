### 1.6 줄간격 지정 (`line_spacing`)

???+ note "줄간격 지정 가이드"

    `line_spacing`은 문단 내 텍스트의 **줄과 줄 사이 간격(행간)**을 설정합니다.

    ---

    **기본 규칙**

    - 숫자 값으로 입력하며, 백분율(%) 로 동작합니다.
    - 값이 클수록 줄 간격이 넓어집니다.
    - 값을 지정하지 않으면 **템플릿에서의 줄간격이 적용**되며, 해당 elements의 text_style을 추가할 경우, **우선 적용** 됩니다.

    ---

    **사용 예시**

    ```json title="line spacing example" hl_lines="12"
    {
      "elements": [
        {
          "placeholder": "desc",
          "type": "text",
          "content": "본 문서는 최근 3년간 교통사고 발생 현황을 정리한 자료입니다.\n각 항목은 경찰청 통계를 기반으로 작성되었습니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "align": "left",
            "multiline": "auto",
            "line_spacing": 120,
            "color": "#000000"
          }
        }
      ]
    }
    ```