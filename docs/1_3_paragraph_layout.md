### 1.3.1 정렬 (`align`)

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

---

### 1.3.2 줄간격 지정 (`line_spacing`)

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
          "content": "줄 간격 지정 테스트입니다.",
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

---

### 1.3.3 문단 간격 지정 (`space_before`, `space_after`)

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

---

### 1.3.4 들여쓰기 (`indent_first`, `indent_left`)

???+ note "들여쓰기 가이드"

    들여쓰기는 문단의 시작 위치를 조정하여  
    문서 구조를 명확하게 표현할 때 사용합니다.

    첫 줄만 들여쓰거나, 문단 전체를 들여쓸 수 있습니다.

    ---

    **지원 속성**

    - `indent_first` : 첫 줄 들여쓰기  
    - `indent_left` : 문단 전체 들여쓰기  

    ---

    **기본 규칙**

    - 숫자 값으로 입력합니다.
    - 단위는 pt 기준입니다.
    - 값이 클수록 들여쓰기 폭이 커집니다.
    - 지정하지 않으면 기본 들여쓰기가 적용됩니다.

    ---

    **동작 방식**

    - `indent_first` → 첫 줄에만 적용  
    - `indent_left` → 모든 줄에 적용  
    - 두 값을 함께 사용하면 누적 적용됩니다.

    ---

    **사용 예시**

    ```json title="text indent example" hl_lines="11-12"
    {
      "elements": [
        {
          "placeholder": "body_indent",
          "type": "text",
          "content": "이 문장은 들여쓰기 예시입니다. 첫 줄과 전체 문단의 시작 위치를 조정할 수 있습니다.",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "align": "left",
            "indent_first": 10,
            "indent_left": 5
          }
        }
      ]
    }
    ```