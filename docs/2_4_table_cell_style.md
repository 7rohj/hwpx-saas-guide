???+ note "셀 스타일 가이드"

    `style.cell`은 표의 **각 셀** 에 대해 **배경색, 표 내부 여백, 텍스트 정렬** 을 설정할 수 있습니다.

    ---

    **기본 규칙**

    - 셀 스타일은 **헤더 영역 과 바디 영역**으로 나눠서 적용할 수 있습니다.
    - `backgroundColor`는 **HEX 색상 입력값**(예: `#FFFFFF`)을 사용합니다.
    - `padding`은 한글의 **[표/셀 속성 > 셀 > 안 여백 지정]** 과 같은 역할입니다.
    - `textAlign`은 셀 안 텍스트의 **가로/세로 정렬**을 지정합니다.

    ---

    **사용 예시**

    ```json title="cell style example" hl_lines="18 19 20 21 22 23 24 25 26 27"
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
        "columnWidths": [50,50,50],
        "border": {
          "outer": { "style": "solid", "width": 0.5, "color": "#000000" },
          "inner": { "style": "solid", "width": 0.5, "color": "#000000" }
        },
        "headerCell": {
          "backgroundColor": "#FF0000",
          "padding": { "left": 1.8, "right": 1.8, "top": 0.5, "bottom": 0.5 },
          "textAlign": { "horizontal": "center", "vertical": "middle" }
        },
        "bodyCell": {
          "backgroundColor": "#4fc8e0",
          "padding": { "left": 1.8, "right": 1.8, "top": 0.5, "bottom": 0.5 },
          "textAlign": { "horizontal": "left", "vertical": "top" }
        }
      }
    }
    ```

---

#### 2.4.1 셀 배경색 (`cell.backgroundColor`)

???+ note "셀 배경색 가이드"

    `cell.backgroundColor`는 셀의 **배경색** 을 지정합니다.  

    ---

    **기본 규칙**

    - HEX값으로 입력해주세요. (예: `"#RRGGBB"`)

    ---

    **사용 예시**

    ```json title="cell background example" hl_lines="19 24"
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
        "columnWidths": [50,50,50],
        "border": {
          "outer": { "style": "solid", "width": 0.5, "color": "#000000" },
          "inner": { "style": "solid", "width": 0.5, "color": "#000000" }
        },
        "headerCell": {
          "backgroundColor": "#FF0000",
          "padding": { "left": 1.8, "right": 1.8, "top": 0.5, "bottom": 0.5 },
          "textAlign": { "horizontal": "center", "vertical": "middle" }
        },
        "bodyCell": {
          "backgroundColor": "#4fc8e0",
          "padding": { "left": 1.8, "right": 1.8, "top": 0.5, "bottom": 0.5 },
          "textAlign": { "horizontal": "left", "vertical": "top" }
        }
      }
    }
    ```

---

#### 2.4.2 셀 안 여백 (`cell.padding`)

???+ note "셀 안 여백(padding) 가이드"

    `cell.padding`은 셀 내부의 **상/하/좌/우 여백**을 지정합니다.  
    한글의 **[표/셀 속성 > 셀 > 안 여백 지정]** 과 같은 역할을 합니다.

    ---

    **기본 규칙**

    - 단위는 **pixel(px)** 입니다.
    - 상하좌우 네 방향 모두 개별 지정 가능합니다.
    - `padding`을 지정한 경우, 한글에서 여백이 보이려면 **“안 여백 지정”이 활성화**되어야 합니다.
        - 라이브러리 정책 상, `cell.padding` 값이 입력되면 자동으로 활성화됩니다.

    ---

    **사용 예시**

    ```json title="cell padding example" hl_lines="20 25"
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
        "columnWidths": [50,50,50],
        "border": {
          "outer": { "style": "solid", "width": 0.5, "color": "#000000" },
          "inner": { "style": "solid", "width": 0.5, "color": "#000000" }
        },
        "headerCell": {
          "backgroundColor": "#FF0000",
          "padding": { "left": 1.8, "right": 1.8, "top": 0.5, "bottom": 0.5 },
          "textAlign": { "horizontal": "center", "vertical": "middle" }
        },
        "bodyCell": {
          "backgroundColor": "#4fc8e0",
          "padding": { "left": 1.8, "right": 1.8, "top": 0.5, "bottom": 0.5 },
          "textAlign": { "horizontal": "left", "vertical": "top" }
        }
      }
    }
    ```

---

#### 2.4.3 셀 텍스트 정렬 (`cell.textAlign`)

???+ note "셀 텍스트 정렬 가이드"

    `cell.textAlign`은 셀 안 텍스트의 **가로/세로 정렬**을 지정합니다.  
    가로는 문단 정렬, 세로는 셀 내부 위치(위/가운데/아래)에 해당합니다.

    ---

    **기본 규칙**

    - 가로 정렬 (`horizontal`)
        - `left` / `center` / `right`
    - 세로 정렬 (`vertical`)
        - `top` / `middle` / `bottom`

    ---

    **사용 예시**

    ```json title="cell text align example" hl_lines="21 26"
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
        "columnWidths": [50,50,50],
        "border": {
          "outer": { "style": "solid", "width": 0.5, "color": "#000000" },
          "inner": { "style": "solid", "width": 0.5, "color": "#000000" }
        },
        "headerCell": {
          "backgroundColor": "#FF0000",
          "padding": { "left": 1.8, "right": 1.8, "top": 0.5, "bottom": 0.5 },
          "textAlign": { "horizontal": "center", "vertical": "middle" }
        },
        "bodyCell": {
          "backgroundColor": "#4fc8e0",
          "padding": { "left": 1.8, "right": 1.8, "top": 0.5, "bottom": 0.5 },
          "textAlign": { "horizontal": "left", "vertical": "top" }
        }
      }
    }
    ```

