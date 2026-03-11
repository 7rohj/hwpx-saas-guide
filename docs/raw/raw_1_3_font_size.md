### 1.3 글꼴 크기 지정 (`font_size`)

???+ note "글꼴 크기 지정 가이드"

    `font_size`는 텍스트의 **글자 크기**를 지정합니다.  
    단위는 **pt(point)** 기준으로 입력합니다.

    문서의 제목, 본문, 각주 등 용도에 따라 크기를 다르게 설정할 수 있습니다.

    ---

    **기본 규칙**

    - 숫자 값으로 입력합니다. (예: 11, 14, 24)
    - 단위는 pt 기준입니다.
    - 지정하지 않으면 템플릿의 기본글꼴 크기가 적용됩니다.

    ---

    **사용 예시**

    ```json title="font size example" hl_lines="9 21"
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
          "placeholder": "body",
          "type": "text",
          "content": "최근 3년간 교통사고 통계입니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "align": "left"
          }
        }
      ]
    }
    ```