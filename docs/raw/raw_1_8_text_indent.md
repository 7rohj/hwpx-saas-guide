### 1.8 들여쓰기 (`indent_first`, `indent_left`)

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