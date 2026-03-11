???+ note "셀 병합 가이드"

    `merge_cells`는 표 내부에서 **여러 셀을 하나로 병합**할 때 사용합니다.  
    시작 좌표(`start`)와 끝 좌표(`end`)를 지정하여 **직사각형 영역**을 병합합니다.

    ---

    **기본 규칙**

    - 좌표는 **[행, 열]** 형식의 **0-based index**를 사용합니다.
        - 예: `[0, 0]` → 첫 번째 행, 첫 번째 열
    - 좌표는 반드시 입력된 `data` 배열 범위 내의 값이어야 합니다.
        - `0 ≤ row < data.length`
        - `0 ≤ col < data[row].length`
    - 범위를 벗어난 좌표가 지정되면 병합은 무시되거나 오류가 발생할 수 있습니다.
    - `start` 좌표는 항상 `end` 좌표보다 **앞쪽(좌상단)** 이어야 합니다.
        - `start.row ≤ end.row`
        - `start.col ≤ end.col`
    - 병합 범위는 **연속된 직사각형 영역**만 허용됩니다.
    - 병합된 영역의 **좌상단 셀 값**이 최종 표시됩니다.
    - 잘못된 좌표 범위가 지정되면 **병합은 무시**되거나 **오류가 발생**할 수 있습니다.

    ---

    **사용 예시**

    ```json title="cell merge example" hl_lines="29 30 31"
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
        "columnWidths": [50, 50, 50],
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
      },
      "merge_cells": [
        { "start": [0, 0], "end": [0, 1] }
      ]
    }
    ```

---

### 2.5.1 병합 좌표 규칙

???+ note "좌표 규칙"

    셀 병합은 **시작 좌표 → 끝 좌표** 순서로 지정합니다.  
    항상 **좌상단 → 우하단 방향**이어야 합니다.

    ---

    **허용 예시**

    ```json
    { "start": [1, 0], "end": [1, 2] }
    ```

    → 같은 행에서 **가로 병합**

    ```json
    { "start": [1, 1], "end": [3, 1] }
    ```

    → 같은 열에서 **세로 병합**

    ```json
    { "start": [1, 0], "end": [3, 2] }
    ```

    → **직사각형 영역 병합**

    ---

    **잘못된 예시**

    ```json
    { "start": [2, 2], "end": [1, 1] }
    ```

    → `start`가 `end`보다 뒤에 있음 ❌

---

### 2.5.2 다중 셀 병합

???+ note "여러 영역 병합"

    `merge_cells` 배열에 여러 병합 영역을 추가할 수 있습니다.

    ```json
    "merge_cells": [
      { "start": [0, 0], "end": [0, 1] },
      { "start": [1, 0], "end": [3, 0] }
    ]
    ```

    - 각 병합 영역은 **서로 겹치지 않아야** 합니다.
    - 겹치는 경우 **결과가 보장되지 않습니다.**
