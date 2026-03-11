???+ note "표 테두리 설정 가이드"

    `border`는 표의 **외곽선, 내부선, 헤더선, 마지막 행 선** 등을  
    **계층적으로 제어**하기 위한 설정입니다.

    단순한 표부터 복잡한 보고서 표까지  
    **하나의 DSL로 모두 표현**할 수 있도록 설계되었습니다.

    `border.outer`과 `border.inner`은 **필수설정**이며,
    `header`, `lastRow`, `borderVariation`은 **선택사항**입니다.

---

#### 2.3.1 선 종류 (`border.style`)

???+ note "테두리 선 종류 가이드"

    `border.style`은 표의 **선 모양**을 지정합니다.  
    대/소문자, 하이픈(`-`), 공백 등은 자동으로 정규화됩니다.

    ---

    **기본 규칙**

    - `style`을 생략하거나 빈 문자열이면 **`solid` (실선)** 으로 처리됩니다.
    - `hidden`과 `none`은 동일하게 **선 없음**을 의미합니다.
    - 일부 **이중선 / 삼중선**은 **굵기 0.3 이상**에서 정상 표현됩니다.

    ---

    **사용 예시**

    ```json title="table border example" hl_lines="16 17 18 19 20 21 22 23 24 25 26 27 28"
    {
      "placeholder": "table_3",
      "type": "table",
      "data": [
        ["구분", "발생건수(건)", "사망자수(명)", "중상자수(명)", "경상자수(명)"],
        ["2021년", "2", "–", "2", "–"],
        ["2022년", "1", "–", "–", "2"],
        ["2023년", "5", "–", "1", "8"]
      ],

      "style": {
        "headerRow": 0,
        "repeatHeader": true,
        "columnWidths": [110,110,110,110,110],

        "border": {
          "outer": { "style": "hidden" },
          "inner": { "style": "solid", "width": 0.12, "color": "#808080" },
          
          "header": {
            "bottom": { "style": "solid", "width": 0.3, "color": "#808080" },
            "verticalInner": { "style": "solid", "width": 0.3, "color": "#FFFFFF" }
          },

          "lastRow": {
            "bottom": { "style": "solid", "width": 0.3, "color": "#808080" }
          }
        },

        "borderVariation": [{ "row": "last", "bottom": { "style": "solid", "width": 0.3, "color": "#808080" } }]
      }
    }
    ```

---

#### 지원되는 선 스타일 목록

| 분류 | `style` 입력값 | 설명 |
|------|----------------|------|
| 1 | `none`, `hidden` | 선 없음 |
| 2 | `solid` | 실선 (기본값) |
| 3 | `dot` | 점선 |
| 4 | `dash` | 파선 |
| 5 | `dash_dot`, `dash-dot`, `dashdot` | `-.-.-.` 형태 |
| 6 | `dash_dot_dot`, `dash-dot-dot`, `dashdotdot` | `-..-..-..` 형태 |
| 7 | `long_dash`, `long-dash`, `longdash` | 더 긴 파선 |
| 8 | `circle`, `circle_dot`, `circle-dot`, `circledot` | 원형 점선 |
| 9 | `double`, `double_slim`, `double-slim` | 이중선 (가는+가는) |
| 10 | `slim_thick`, `slim-thick`, `thinbold` | 이중선 (가는+굵은) |
| 11 | `thick_slim`, `thick-slim`, `boldthin` | 이중선 (굵은+가는) |
| 12 | `slim_thick_slim`, `slim-thick-slim`, `thinboldthin` | 삼중선 (가는+굵은+가는) |

---

#### 2.3.2 외곽선과 내부선 (`outer`, `inner`)

???+ note "기본 테두리 구조"

    `border.outer`는 **표 전체 외곽선**,  
    `border.inner`는 **셀 사이 내부선**을 의미합니다.

    ---

    **사용예시**

    ```json title="basic border example"
    "border": {
      "outer": { "style": "hidden" },
      "inner": { "style": "solid", "width": 0.12, "color": "#808080" }
    }
    ```

---

#### 2.3.3 헤더선과 마지막 행 (`header`, `lastRow`)

???+ note "특정 영역 선 제어"

    표 스타일 꾸밈의 폭을 늘리기 위해 헤더 행과 표의 마지막 행 블록을 따로 제공합니다.

    ---

    **지원 속성**

    - `header.bottom` → **헤더 전체 하단선**
    - `header.verticalInner` → **헤더 내부 세로선**
    - `lastRow.bottom` → **표 마지막 행 하단선**

    ---

    **사용 예시**

    ```json title="header / lastRow example"
    "border": {
      "outer": { "style": "hidden" },
      "inner": { "style": "solid", "width": 0.12, "color": "#808080" },

      "header": {
        "bottom": { "style": "solid", "width": 0.3, "color": "#808080" },
        "verticalInner": { "style": "solid", "width": 0.3, "color": "#FFFFFF" }
      },

      "lastRow": {
        "bottom": { "style": "solid", "width": 0.3, "color": "#808080" }
      }
    }
    ```

---

#### 2.3.4 셀 단위 커스터마이징 (`borderVariation`)

???+ note "세밀한 선 제어"

    `borderVariation`은  
    **특정 행 / 열 / 범위의 선을 개별적으로 변경**할 때 사용합니다.

    `borderVariation`은 `border`과 같은 계층에 위치하여 작성합니다.

    기본 `border` 설정보다 **우선 적용**됩니다.

    ---

    **지원 속성**

    - `"row": 숫자`
    - `"row": "last"` → 마지막 행
    - `"col": 숫자`
    - `"range": [rowStart, colStart, rowEnd, colEnd]`

    ---

    **사용 예시**

    ```json title="border variation example"
    "borderVariation": [

      { "row": 0, "bottom": { "style": "solid", "width": 0.3, "color": "#808080" } },

      { "row": 0, "col": 0, "right": { "style": "solid", "width": 0.3, "color": "#FFFFFF" } },
      { "row": 0, "col": 1, "left":  { "style": "solid", "width": 0.3, "color": "#FFFFFF" } },

      { "range": [1, 0, 9999, 9999], "bottom": { "style": "solid", "width": 0.12, "color": "#808080" } },

      { "row": "last", "bottom": { "style": "solid", "width": 0.3, "color": "#808080" } }
    ]
    ```

---

#### 2.3.5 두 방식의 호환성

???+ note "권장 DSL 구조"

    현재 시스템은 다음 **두 가지 방식**을 모두 지원합니다.

    - **구조형 DSL (`header`, `lastRow`)**  
    → 가독성 높음, 권장 방식

    - **좌표 기반 DSL (`borderVariation`)**  
    → 레거시 호환 및 정밀 제어

    두 방식은 **동시에 사용 가능**하며  
    **`borderVariation`이 최종 우선순위**를 가집니다.