???+ note "텍스트 생성 가이드"

    텍스트는 문서 내 **지정된 위치에 문자열을 삽입**하는 기능입니다.  
    단일 문장부터 여러 줄 텍스트까지 간단하게 생성할 수 있습니다.

    ---

    **기본 규칙**

    - 텍스트는 `elements` 배열 내부에서 **`type: "text"`** 로 선언합니다.
    - 실제 문자열은 **`content`** 필드에 작성합니다.
    - 줄바꿈이 필요한 경우 `\n` 을 사용할 수 있습니다.
    - 스타일 적용 시 `style` 객체를 선택적으로 사용할 수 있습니다.

    ---

    **사용 예시**

    ```json title="text create example" hl_lines="5"
    {
      "elements": [
        {
          "placeholder": "title",
          "type": "text",
          "content": "문서제목입니다."
        }
      ]
    }
    ```
