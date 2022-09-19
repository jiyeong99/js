## EventTarget.addEventListener()
- 지정한 유형의 이벤트를 대상이 수신할 때마다 호출할 함수를 설정합니다.
- 일반적인 대상은 Element, Document, Window지만, XMLHttpRequest와 같이 이벤트를 지원하는 모든 객체가 대상이 될 수 있습니다.
- 지정한 이벤트 유형의EventTarget 수신기 리스트에 EventListener를 구현한 함수 또는 객체를 추가하는 방식으로 동작
- 추가한 수신기를 반드시 removeEventListener()로 직접 제거해야 하는 것은 아닙니다.
```
addEventListener(type, listener);
addEventListener(type, listener, options);
addEventListener(type, listener, useCapture);
```
### 매개변수
#### type
- 수신할 이벤트 유형을 나타내는 대소문자 구분 문자열입니다.
#### listener
- 지정한 이벤트(Event 인터페이스를 구현한 객체)를 수신할 객체입니다.
- handleEvent() 메서드를 포함하는 객체 또는 JavaScript 함수여야 합니다
 #### options
- 이벤트 수신기의 특징을 지정할 수 있는 객체입니다. 
##### capture
- 이벤트 대상의 DOM 트리 하위에 위치한 자손 EventTarget으로 이벤트가 전달되기 전에, 이 수신기가 먼저 발동돼야 함을 나타내는 불리언 값입니다. 
- 명시하지 않을 경우 기본 값은 false입니다.
##### once
- 수신기가 최대 한 번만 동작해야 함을 나타내는 불리언 값입니다. 
- true를 지정할 경우, 수신기가 발동한 후에 스스로를 대상에서 제거합니다. 
- 명시하지 않을 경우 기본 값은 false입니다.
##### passive
- true일 경우, 이 수신기 내에서 preventDefault()를 절대 호출하지 않을 것임을 나타내는 불리언 값입니다. 
- 이 값이 true인데 수신기가 preventDefault()를 호출하는 경우, 사용자 에이전트는 콘솔에 경고를 출력하는 것 외에 아무런 동작도 하지 않습니다.
- 명시하지 않을 경우의 기본 값은 false지만, Safari와 Internet Explorer를 제외한 브라우저에서 wheel (en-US), mousewheel (en-US), touchstart, touchmove (en-US) 이벤트에서의 기본 값은 true입니다.
##### signal
- AbortSignal입니다. 
- 지정한 AbortSignal 객체의 abort() 메서드를 호출하면 이 수신기가 제거됩니다. 
- 명시하지 않을 경우 이벤트 수신기가 아무 AbortSignal에도 연결되지 않습니다.
##### useCapture Optional
- 이벤트 대상의 DOM 트리 하위에 위치한 자손 EventTarget으로 이벤트가 전달되기 전에, 이 수신기가 먼저 발동돼야 함을 나타내는 불리언 값입니다. 
- 캡처 모드인 수신기는 DOM 트리의 위쪽으로 버블링 중인 이벤트에 의해선 발동하지 않습니다. 
- 이벤트 버블링과 캡처링은 조상-자손 관계를 가진 두 개의 요소가 동일한 이벤트 유형에 대한 수신기를 가지고 있을 때, 두 요소에 이벤트가 전파되는 방법을 말합니다.
- 이벤트 전파 모드에 따라 두 요소 중 이벤트를 먼저 수신하는 쪽이 달라집니다. 
- 기본 값은 false입니다.
## 이벤트 참조
[참조링크 - 표준 이벤트 참조](https://developer.mozilla.org/ko/docs/Web/Events)
