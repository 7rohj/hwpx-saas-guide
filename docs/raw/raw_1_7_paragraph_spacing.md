### 1.7 문단 간격 지정 (`space_before`, `space_after`)

???+ note "문단 간격 지정 가이드"

    `space_before`, `space_after`는 문단의 **위쪽 / 아래쪽 여백**을 설정합니다.

    문단 사이의 간격을 조절하여 문서의 가독성과 레이아웃을 개선할 수 있습니다.

    ---

    **지원 속성**

    - `space_before` : 문단 위쪽 여백  
    - `space_after` : 문단 아래쪽 여백  

    ---

    **기본 규칙**

    - 숫자 값으로 입력합니다.
    - 단위는 pt 기준입니다.
    - 지정하지 않으면 기본 문단 간격이 적용됩니다.
    - 줄간격(`line_spacing`)과는 별도로 동작합니다.

    ---

    **사용 예시**

    ```json title="paragraph spacing example" hl_lines="11-12"
    {
      "elements": [
        {
          "placeholder": "acs",
          "type": "text",
          "content": "문단 위아래 간격 테스트입니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "align": "center",
            "space_before": 10,
            "space_after": 12
          }
        }
      ]
    }
    ```