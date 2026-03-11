### 1.1 문자 서식 적용 (`text emphasis`)

???+ note "문자 서식 적용 가이드"

    텍스트 요소의 `style` 속성을 통해  
    **볼드, 이탤릭, 밑줄** 서식을 적용할 수 있습니다.

    ---

    **지원 속성**

    - `bold` : 굵게 표시  
    - `italic` : 기울임 표시  
    - `underline` : 밑줄 표시  

    각 속성은 `true / false` 값으로 설정합니다.

    ---

    **기본 규칙**

    - 여러 서식을 동시에 조합할 수 있습니다.
    - 지정하지 않은 속성은 기본값(false)이 적용됩니다.
    - 텍스트 정렬(`align`) 및 색상(`color`)과 함께 사용 가능합니다.

    ---

    **사용 예시**

    ```json title="text emphasis example" hl_lines="10 23-24"
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
            "underline": true,
            "align": "center",
            "color": "#666666"
          }
        }
      ]
    }
    ```