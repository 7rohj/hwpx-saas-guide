### 1.4 글꼴 색상 지정 (`color`)

???+ note "글꼴 색상 지정 가이드"

    `color`는 텍스트의 **글자 색상**을 지정합니다.  
    HEX 형식으로 설정할 수 있습니다.

    ---

    **기본 규칙**

    - HEX 형식: `"#RRGGBB"`  
    - 문자열 형태로 입력합니다.
    - 지정하지 않으면 기본 색상인 검정으로 적용됩니다.

    ---

    **사용 예시**

    ```json title="font color example" hl_lines="12 25"
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
            "align": "center",
            "color": "#000000"
          }
        },

        {
          "placeholder": "subtitle",
          "type": "text",
          "content": "2021년 ~ 2023년 통계",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 14,
            "italic": true,
            "align": "center",
            "color": "#666666"
          }
        }
      ]
    }
    ```