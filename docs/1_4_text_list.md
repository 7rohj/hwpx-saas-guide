### 1.4.1 글머리 기호 및 번호 매기기 (`list_type`)

???+ note "목록(리스트) 가이드"

    텍스트 요소에 **글머리 기호(bullet)** 또는  
    **번호 매기기(numbering)** 목록 스타일을 적용할 수 있습니다.

    항목 나열, 단계 설명, 체크리스트 표현 등에 사용됩니다.

    ---

    **지원 속성**

    - `list_type` : 목록 유형 지정  
    - `list_level` : 목록 들여쓰기 단계 (선택)

    ---

    **지원 값**

    `list_type` 값:

    - `"bullet"` : 글머리 기호  
    - `"number"` : 번호 매기기  

    ---

    **기본 규칙**

    - 목록은 각 항목을 개별 `text` 요소로 구성합니다.
    - 같은 목록 그룹은 동일한 `list_level` 값을 사용하는 것을 권장합니다.
    - 지정하지 않으면 일반 문단으로 표시됩니다.

    ---

    **사용 예시**

    ```json title="text list example" hl_lines="10-11 21-22 32-33"
    {
      "elements": [
        {
          "placeholder": "item1",
          "type": "text",
          "content": "데이터 수집",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "list_type": "number",
            "list_level": 1
          }
        },
        {
          "placeholder": "item2",
          "type": "text",
          "content": "데이터 정제",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "list_type": "number",
            "list_level": 1
          }
        },
        {
          "placeholder": "item3",
          "type": "text",
          "content": "결과 분석",
          "style": {
            "font_family": "맑은 고딕",
            "font_size": 11,
            "list_type": "bullet",
            "list_level": 1
          }
        }
      ]
    }
    ```