???+ note "표 레이아웃 가이드"

    표 레이아웃은 **행/열 구조, 너비, 높이, 병합** 등 을 수정할 수 있습니다.

    또한, 생성된 표 내부에는 `style` 설정을 통해  
    **헤더, 열 너비, 표 테두리 스타일, 셀 배경색, 셀 내 여백, 텍스트 정렬** 등을  
    추가로 지정할 수 있습니다.

---

#### 2.2.1 헤더 행 지정 (`headerRow`)

???+ note "헤더 행 지정 가이드"

    `headerRow`는 **헤더로 처리할 행의 인덱스**를 지정합니다.

    ---

    **기본 규칙**

    - 인덱스는 **0부터 시작**하며, 기본값 0 입니다.
    - 지정된 행은 **페이지 분할 시 반복 대상**이 됩니다.

    ---

    **사용 예시**

    ```json title="headerRow example" hl_lines="11"
    {
      "placeholder": "table_3",
      "type": "table",
      "data": [
        ["구분", "항목", "금액"],
        ["1", "품목A", "100,000"],
        ["2", "품목C", "200,000"],
        ["3", "품목D", "300,000"]
      ],
      "style": {
        "headerRow": 0,
        "repeatHeader": true,
        "columnWidths": [50, 50, 50]
      }
    }
    ```

---

#### 2.2.2 헤더 반복 (`repeatHeader`)

???+ note "헤더 반복 가이드"

    `repeatHeader=true`이면 **페이지 경계에서 표가 분할될 때  
    헤더 행이 다음 페이지에도 자동 반복**됩니다.

    ---

    **기본 규칙**

    - `headerRow`가 지정된 경우에만 동작합니다.
    - 기본값 true 입니다.

    ---

    **사용 예시**

    ```json title="repeatHeader example" hl_lines="12"
    {
      "placeholder": "table_3",
      "type": "table",
      "data": [
        ["구분", "항목", "금액"],
        ["1", "품목A", "100,000"],
        ["2", "품목C", "200,000"],
        ["3", "품목D", "300,000"]
      ],
      "style": {
        "headerRow": 0,
        "repeatHeader": true,
        "columnWidths": [50, 50, 50]
      }
    }
    ```
    
---

#### 2.2.3 열 너비 지정 (`columnWidths`)

???+ note "열 너비 지정 가이드"

    `columnWidths`는 **각 열의 너비**를 배열로 지정합니다.

    ---

    **기본 규칙**

    - 배열 길이는 **표의 열 개수와 반드시 동일**해야 합니다.
    - **mm** 기반으로 입력해주세요.

    **사용 예시**

    ```json title="column width example" hl_lines="13"
    {
      "placeholder": "table_3",
      "type": "table",
      "data": [
        ["구분", "항목", "금액"],
        ["1", "품목A", "100,000"],
        ["2", "품목C", "200,000"],
        ["3", "품목D", "300,000"]
      ],
      "style": {
        "headerRow": 0,
        "repeatHeader": true,
        "columnWidths": [50, 50, 50]
      }
    }
    ```

---

#### 2.2.4 스타일 확장 (`style`)

???+ note "스타일 확장"

    표 생성 이후 아래의 `style` 속성을 추가할 수 있습니다.

    - [표 테두리 설정](../2_3_table_border_style/)    
         - 선 스타일 (`border.style`)  
         - 선 굵기 (`border.width`)  
         - 선 색상 (`border.color`)
    - [셀 스타일](../2_4_table_cell_style/)   
        - [셀 배경색 (`cell.backgroundColor`)](../2_4_table_cell_style/#241-cellbackgroundcolor)
        - [셀 내부 여백 지정 (`cell.padding`)](../2_4_table_cell_style/#242-cellpadding)
        - [셀 텍스트 정렬 (`cell.textAlign`)](../2_4_table_cell_style/#243-celltextalign)
