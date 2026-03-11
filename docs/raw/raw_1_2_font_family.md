### 1.2 글꼴 종류 지정 (`font_family`)

???+ note "글꼴 지정 가이드"

    `font_family`는 텍스트에 적용할 **글꼴(폰트) 이름**을 지정합니다.

    문서의 용도에 따라 제목용, 본문용 글꼴을 구분하여 사용할 수 있습니다.

    ---

    **기본 규칙**

    - 글꼴 이름은 문자열로 입력합니다.
    - 시스템 또는 문서에서 지원하는 글꼴이어야 정상 표시됩니다.
    - 지정하지 않으면 기본 글꼴이 적용됩니다.

    ---

    **사용 가능한 예시 글꼴**

    - 맑은 고딕  
    - 바탕체  
    - 돋움체  
    - Arial  
    - Times New Roman  

    (※ 실제 표시 가능 여부는 문서 환경에 따라 달라질 수 있습니다.)

    ---

    **사용 예시**

    ```json title="font family example" hl_lines="8 20"
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
            "font_family": "바탕체",
            "font_size": 11,
            "align": "left"
          }
        }
      ]
    }
    ```