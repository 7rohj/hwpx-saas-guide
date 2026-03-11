### 1.9 배경색 / 형광펜 효과 (`background_color`)

???+ note "텍스트 배경색 가이드"

    `background_color`는 텍스트 뒤에 **배경색(형광펜 효과)**을 적용합니다.

    중요한 문구 강조, 상태 표시, 하이라이트 표현 등에 활용할 수 있습니다.

    ---

    **기본 규칙**

    - HEX 형식 또는 RGB 형식으로 입력합니다.
    - 문자열 형태로 지정합니다.
    - 지정하지 않으면 배경색은 적용되지 않습니다.

    ---

    **지원 형식**

    - HEX: `"#RRGGBB"`  
    - RGB: `"rgb(r,g,b)"`

    ---

    **사용 예시**

    ```json title="text background example" hl_lines="11 23"
    {
      "elements": [
        {
          "placeholder": "highlight_text",
          "type": "text",
          "content": "중요 안내 문구입니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "bold": true,
            "background_color": "#FFF2CC",
            "color": "#000000"
          }
        },

        {
          "placeholder": "highlight_text_rgb",
          "type": "text",
          "content": "RGB 형식 배경색 예시입니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "background_color": "rgb(255,230,153)"
          }
        }
      ]
    }
    ```