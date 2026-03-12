### 1.2.1 문자 서식 적용 (`text emphasis`)

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
          "content": "제목 예시",
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
          "content": "서브 타이틀입니다.",
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

---

### 1.2.2 글꼴 종류 지정 (`font_family`)

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
          "content": "제목 예시",
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
          "content": "본문입니다.",
          "style": {
            "font_family": "바탕체",
            "font_size": 11,
            "align": "left"
          }
        }
      ]
    }
    ```

---

### 1.2.3 글꼴 크기 지정 (`font_size`)

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
          "content": "제목 예시",
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
          "content": "본문입니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "align": "left"
          }
        }
      ]
    }
    ```

---

### 1.2.4 글꼴 색상 지정 (`color`)

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
          "content": "제목 예시",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 24,
            "bold": true,
            "align": "center",
            "color": "#000000"
          }
        },

        {
          "placeholder": "body",
          "type": "text",
          "content": "본문입니다",
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

---

### 1.2.5 배경색 / 형광펜 효과 (`background_color`)

???+ note "텍스트 배경색 가이드"

    `background_color`는 텍스트 뒤에 **배경색(형광펜 효과)**을 적용합니다.

    중요한 문구 강조, 상태 표시, 하이라이트 표현 등에 활용할 수 있습니다.

    ---

    **지원 속성**

    - HEX: `"#RRGGBB"`  
    - RGB: `"rgb(r,g,b)"`

    ---

    **기본 규칙**

    - HEX 형식 또는 RGB 형식으로 입력합니다.
    - 문자열 형태로 지정합니다.
    - 지정하지 않으면 배경색은 적용되지 않습니다.

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

---

### 1.2.6 위첨자 / 아래첨자 (`superscript`, `subscript`)

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

    ```json title="superscript subscript example" hl_lines="10 21"
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