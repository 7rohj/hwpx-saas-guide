### 1.10 위첨자 / 아래첨자 (`superscript`, `subscript`)

???+ note "위첨자 / 아래첨자 가이드"

    `superscript`, `subscript`는 텍스트를 **위첨자** 또는 **아래첨자** 형태로 표시합니다.

    수식, 각주 표시, 화학식 등 특수 표기에 사용됩니다.

    ---

    **지원 속성**

    - `superscript` : 위첨자 표시  
    - `subscript` : 아래첨자 표시  

    각 속성은 `true / false` 값으로 설정합니다.

    ---

    **기본 규칙**

    - 두 속성은 동시에 사용할 수 없습니다.
    - 지정하지 않으면 일반 텍스트로 표시됩니다.
    - 문자 단위 강조에 주로 사용됩니다.

    ---

    **사용 예시**

    ```json title="superscript subscript example" hl_lines="11 23"
    {
      "elements": [
        {
          "placeholder": "sup_example",
          "type": "text",
          "content": "m2",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "superscript": true
          }
        },

        {
          "placeholder": "sub_example",
          "type": "text",
          "content": "H2O",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "subscript": true
          }
        }
      ]
    }
    ```