### 1.5 정렬 (`align`)

???+ note "텍스트 정렬 가이드"

    `align`은 문단 내 텍스트의 **가로 정렬 방식**을 지정합니다.

    제목, 본문, 표 설명 등 문서 레이아웃에 맞게 정렬을 설정할 수 있습니다.

    ---

    **지원 속성**

    - `"left"` : 왼쪽 정렬  
    - `"center"` : 가운데 정렬  
    - `"right"` : 오른쪽 정렬  
    - `"justify"` : 양쪽 정렬  

    ---

    **기본 규칙**

    - 문자열 값으로 입력합니다.
    - 지정하지 않으면 기본 정렬인 왼쪽으로 적용됩니다.
    - 플레이스홀더 단위로 적용됩니다.

    ---

    **사용 예시**

    ```json title="text alignment example" hl_lines="11 22 33"
    {
      "elements": [
        {
          "placeholder": "title",
          "type": "text",
          "content": "교통사고 발생 현황",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 24,
            "bold": true,
            "align": "center"
          }
        },

        {
          "placeholder": "body_left",
          "type": "text",
          "content": "왼쪽 정렬 본문입니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "align": "left"
          }
        },

        {
          "placeholder": "body_justify",
          "type": "text",
          "content": "양쪽 정렬이 적용된 문단 예시입니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "align": "justify"
          }
        }
      ]
    }
    ```