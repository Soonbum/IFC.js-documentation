# 소개

IFC.js는 브라우저에서 IFC 모델을 로드하고 표시하고 편집할 수 있는 JavaScript 라이브러리입니다. 당신의 IFC 모델을 가지고 [라이브 데모](https://ifcjs.github.io/web-ifc-viewer/example/index)를 열어보시고 IFC.js의 능력을 발견해 보십시오.

## 이 라이브러리는 무엇입니까?

### IFC란 무엇입니까?

건축가와 엔지니어들은 건물 도면을 하나씩 그리곤 했습니다. 이제는 아닙니다! BIM (Building Information Modeling)을 통해 건축가와 엔지니어들은 이제 프로젝트의 모델들을 만듭니다. 이 모델들은 프로젝트를 실현하는 데 필요한 형상과 정보가 모두 포함되어 있으며 요람에서 무덤까지 프로젝트 전반에 걸쳐 모든 정보의 허브가 되어야 합니다.

그러나 건물은 너무 복잡하여 이러한 모델 전체를 생성할 수 있는 단일 애플리케이션이 없습니다. 각 애플리케이션은 형상 모델링, 구조 계산, 에너지 시뮬레이션, 프로젝트 문서 작성 등 각각의 특정 임무가 있습니다.

이 도구들은 전 세계의 여러 개발자들이 만들었고 각각의 도구들은 각자의 포맷으로 작동동합니다. 즉, 구조 계산 애플리케이션이 생성한 구조 모델은 에너지 시뮬레이션 소프트웨어로 읽을 수 없으며 그 반대의 경우도 마찬가지입니다. 그렇다면 어떻게 건물 모델을 여러 도구들로부터 만들 수 있습니까?

그 해답은 [IFC](https://www.buildingsmart.org/standards/bsi-standards/industry-foundation-classes/)입니다. 이것은 건물의 3D 모델을 포함시키기 위해 BuildingSMART가 만든 포맷입니다. 이것은 개방되어 있으므로 아무나 읽고 쓸 수 있습니다. 얏호!

* IFC 덕분에 모든 개발자는 건설 분야의 대형 개발 회사의 앱과 통신할 수 있는 BIM 앱을 자유롭게 만들 수 있습니다.

### IFC의 문제점

BIM 애플리케이션을 만들고 싶은 사람은 다른 도구들에서 정보를 가져오고 내보낼 수 있도록 **IFC 파일을 읽고 작성해야 합니다.** 불행히도 IFC는 읽고 쓰기 어려운 포맷입니다. 수천 페이지의 문서가 있으며 자체 제작된 IFC 파서를 만들고 유지보수하는 것은 엄청난 작업입니다.

* IFC를 감당할 수 있겠습니까? 이것은 풀타임 개발자가 여러 명 있는 회사만 어떻게든 해볼 수 있습니다. 더 이상 개방형이라는 생각이 들지 않죠?

IFC의 내부가 어떻게 생겼는지 궁금하다면 다음에 예시가 있습니다. 다음과 같은 수십만 개의 라인을 파싱한다고 상상해 보십시오:

```
#6699= IFCCARTESIANPOINT((0.,-1.7053025E-13));
#6701= IFCAXIS2PLACEMENT2D(#6699,#23);
#6703= IFCCARTESIANPOINT((892.,-253.399999,150.));
#6705= IFCAXIS2PLACEMENT3D(#6703,#15,#19);
#6706= IFCEXTRUDEDAREASOLID(#6702,#6705,#19,506.8);
#6707= IFCCOLOURRGB($,0.50196,0.501913,0.501960);
```

설령 맨 처음부터 파서를 만들고 IFC 스키마의 모든 변경 사항을 유지 보수하려고 하더라도 이 문제를 해결하기 위한 몇 가지 중요한 질문이 있습니다. 매우 큰 파일에서 메모리를 어떻게 관리할 수 있습니까? 기하학적 생성을 어떻게 효율적으로 구현하겠습니까? IFC가 올바르게 정의되지 않은 경우 무엇을 해야 합니까?

### 당신을 구출하기 위한 IFC.js

모든 개발자가 자신이 만든 애플리케이션에 대해 자신만의 IFC 파일 판독기/작성기를 구현해야 한다는 것은 말이 안 됩니다. 특히 우리 모두가 같은 것을 원할 경우 더더욱 그렇습니다: **지오메트리와 데이터 가져오기/내보내기.**

* IFC.js는 **IFC 파일을 읽고 쓰는 것을** 매우 쉽게 만들어주는 JavaScript 라이브러리입니다.

이를 통해 건축/건설 애플리케이션 개발자는 IFC에서 쉽게 작업하고 비즈니스에 가치를 더하는 기능에 집중할 수 있습니다.

## IFC.js 요약

IFC.js는 2가지에 집중합니다:

* 기하: IFC.js는 Three.js 또는 Babylon.js와 같은 3D 라이브러리와 호환되기 때문에 3D 장면을 생성할 수 있습니다. 이것은 3D BIM 도구를 즉시 만들 수 있다는 것을 의미합니다.

* 데이터: 상기 기하와 연관된 모든 속성들에 대한 고수준 접근을 제공합니다. 이것은 건물 구성요소, 재질, 열 특성, 구조적 강도 등에 대한 데이터에 쉽게 접근할 수 있다는 것을 의미합니다.

IFC.js로 BIM 애플리케이션을 만드는 것은 JavaScript, HTML, CSS로 웹 페이지를 만드는 것처럼 쉽습니다.

```javascript
import { IfcLoader } from "web-ifc-three";
import { Scene } from "three";

// THREE.js 장면 생성하기
const scene = new Scene();

// ...

// IFC를 로드하고 장면에 그것을 추가함
const ifcLoader = new IfcLoader();
ifcLoader.load(ifcURL, (geometry) => scene.add(geometry));
```

## 이 라이브러리는 누구를 위한 것입니까?

이 라이브러리는 BIM 애플리케이션을 개발하고 싶은 모든 이들을 위한 것입니다. 여기에는 건설업계, 건축가 및 IFC 파일의 데이터를 활용하려는 기타 전문가를 위한 애플리케이션을 만드는 개발자들이 모두 포함됩니다.

이 라이브러리를 사용하려면 JavaScript, HTML, CSS에 대한 기본 지식이 필요합니다. 이 지식은 이 문서의 범위를 벗어납니다. 또한 IFC의 지오메트리를 표시하려면 몇 가지 3D 라이브러리도 사용해야 합니다. (Three.js 또는 Babylon.js)

만약 어디서부터 시작해야 할지 모르겠다면, [여기](https://threejs.org/manual/)를 보시거나 [디스코드 채널](https://discord.gg/FXfyR4XrKT)에 가입해서 "하이"라고 인사부터 해보세요.

## IFC.js는 왜 다릅니까?

IFC.js는 JavaScript에 의해 작성된 라이브러리이며 틀림없이 가장 널리 쓰이는 언어 중 하나입니다. 이는 웹 브라우저, 데스크톱 및 모바일 애플리케이션과 호환된다는 것을 의미합니다. JavaScript는 가장 배우기 쉬운 언어 중 하나이며 HTML 및 CSS로 사용자 인터페이스를 구축할 수 있습니다. 즉, IFC.js로 BIM 애플리케이션을 만드는 것은 웹 페이지를 만드는 것만큼이나 쉽습니다.

### 멀티플랫폼

당신은 어떤 플랫폼에서나 개방형 BIM 애플리케이션을 만들기 위해 IFC.js를 사용할 수 있습니다:
|프론트엔드|백엔드|PC|모바일|
|--|--|--|--|
|**바닐라 JavaScript** 또는 **React, Vue, Angular, Svelte 등**과 같은 다른 도구들을 사용하여 서버 통신에 의존하지 않고도 IFC 파일을 읽거나 쓰고 3D를 표시하는 **프론트엔드 웹 애플리케이션**을 만들 수 있습니다. 즉, *IFC.js가 있으면 어떤 웹 브라우저라도 개방형 BIM 앱으로 전환할 수 있습니다.*|클라이언트에서 IFC 파일을 처리할 수 없는 경우가 있을 수 있습니다. 예를 들어, 모바일 장치는 여러 개의 중/대규모 IFC를 표시할 수 있는 능력을 갖고 있지 않을 수 있습니다. 이 경우 [Node.js](https://nodejs.org/en/)를 통해 **서버 상에서 IFC.js를 사용**하고 이미 준비된 Three.js 장면을 클라이언트에게 보내면 가능합니다.|웹 애플리케이션 대신 **Windows, iOS, Linux에서 실행가능한 네이티브 데스크톱 애플리케이션**을 만들고 싶을 때가 있습니다. [Electron](https://www.electronjs.org/)과 같은 기술 덕분에 그것이 가능합니다. 이 네이티브 애플리케이션은 웹 애플리케이션과 같은 방식으로 만들 수 있습니다; HTML, CSS, JavaScript, React, Vue 등|IFC.js는 WebGL 코드와 네이티브 OpenGL을 매핑시키는 [React Native](https://reactnative.dev/)도 지원합니다. 이것은 IFC-호환 **안드로이드/iOS에서 실행되는 개방형 BIM 앱**을 쉽게 만들 수 있음을 의미합니다.|

### 속도

웹 애플리케이션에 대한 경험이 있다면 JavaScript 기반 IFC 라이브러리의 약점은 성능이라고 생각할 수도 있습니다. 그러나 라이브러리의 코어는 WebAssembly와 [Emscripten](https://emscripten.org/)과 결합된 C++로 개발되었습니다. IFC.js가 브라우저에서 직접 실행되는 동안 데스크톱 애플리케이션의 속도와 성능에 접근하기 위해 **최대 성능**을 낼 수 있도록 특별히 설계되었습니다.

### 기능

* IFC.js는 IFC 파일을 원활하게 **읽을** 수 있습니다.

* 브라우저에서 60 fps로 실행되는 **3D 지오메트리**를 생성합니다.

* Three.js의 능력을 이용하여 지오메트리 **외형**을 쉽게 편집할 수 있습니다.

* **여러 개**의 연합 IFC 모델들을 로드합니다.

* 보고서 및 데이터베이스에 대한 **IFC 속성**을 가져옵니다.

* 또한 IFC.js는 맨 처음부터 IFC 파일을 **편집하고 작성**할 수도 있습니다.

## 소스 코드

IFC.js는 대규모 다중 언어 라이브러리입니다. (C++, TypeScript JavaScript, 등) 이것을 하나의 리포지토리 안에 두는 것은 어렵고 다루기 힘들 수 있습니다. 그러한 이유로 인해 이 라이브러리는 여러 개의 리포지토리로 나눠져 있으며 각각은 자신만의 목적을 갖고 있습니다. [여기](https://github.com/IFCjs)에서 찾아보실 수 있습니다.

|web-ifc|web-ifc-three|web-ifc-viewer|
|--|--|--|
|라이브러리의 코어입니다: 맨 처음부터 C++로 작성된 IFC **파서/지오메트리 생성자**이며 Emscripten을 통해 WebAssembly로 컴파일되었습니다. 이 리포지토리는 IFC 파일을 읽는 부분과 데이터를 메모리로 로딩하는 부분의 복잡성을 캡슐화하였습니다.|이 라이브러리는 web-ifc를 Three.js에 적용시켜 **사용자가 IFC와 직접 상호작용할 수 있는 최적화된 3D 장면**을 생성합니다. 이 라이브러리는 [공식 Three.js IFC 로더](https://threejs.org/examples/webgl_loader_ifc.html)입니다. 이 어댑터 덕분에 단 2줄의 코드로 Three.js를 통해 개방형 BIM 애플리케이션을 만들 수 있습니다.|이것은 **IFC.js로 수행할 수 있는 많은 예제들**이 포함된 브라우저 기반 [IFC 뷰어](https://ifcjs.github.io/web-ifc-viewer/example/index)입니다. 장면 탐색, 재질 변경, 클릭에 의한 요소 선택, 단면도 등을 표현할 수 있습니다. 이 리포지토리에는 이 모든 기능에 대한 예제가 있으므로 개방형 BIM 애플리케이션에서 창의적으로 재사용할 수 있습니다.|

## 기여

IFC.js를 통해 개방형 BIM 개발의 세상을 개선할 수 있도록 저희를 돕고 싶으십니까? 라이브러리의 규모가 크기 때문에 참여하고 싶은 것을 선택하셔야 할 것입니다.

* 코딩은 못하지만 참여하고 싶다: 좋습니다! 코딩 외에도 당신이 할 수 있는 것들이 많이 있습니다. [디스코드 채널](https://discord.gg/FXfyR4XrKT)에 들어가서 방법을 찾아보십시오.

* 파싱, 지오메트리, C++: 만약 당신이 C++, WebAssembly, 파싱 또는 IFC의 본질적인 부분에 대해 열정적이라면, 이 업계에서 가장 빠른 오픈 소스 BIM 파서를 이용해 저희를 도우실 수 있습니다: [web-ifc](https://github.com/tomvandig/web-ifc).

* Three.js, 지오메트리, Typescript: 만약 당신이 Three.js 개발자라면, [공식 Three.js IFC 로더](https://threejs.org/examples/webgl_loader_ifc.html)인 [web-ifc-three](https://github.com/IFCjs/web-ifc-three)로 저희를 도우실 수 있습니다.

* BIM 도구, 브레인스토밍, UX: 만약 당신이 근사한 개방형 BIM 애플리케이션을 만드는 데 관심이 있고 BIM 도구나 사용자 인터페이스에 대한 훌륭한 아이디어를 갖고 있다면, [web-ifc-viewer](https://github.com/IFCjs/web-ifc-viewer)가 시장에서 가장 좋은 IFC 뷰어가 되도록 저희를 도와 주십시오.

어쨌든 당신이 [디스코드 채널](https://discord.gg/FXfyR4XrKT)에 들러서 인사 좀 하고 당신의 생각을 들려 주셨으면 합니다. 그러면 저희는 몇 가지 지침을 줄 수 있습니다.

---

# Hello world

## 소개

IFC.js로 BIM 애플리케이션을 만드는 것은 매우 쉽습니다. [여기](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-three/helloworld)에서 가이드의 전체 프로젝트를 찾을 수 있고, [여기](https://ifcjs.github.io/hello-world/examples/web-ifc-three/helloworld/)에서 배치된 애플리케이션을 찾을 수 있습니다. 당신은 그저 Node.js와 아무 IDE를 설치하기만 하고 다음 단계를 따라오시면 됩니다. 또 필요한 실습용 IFC 파일이 없다면 [여기](https://github.com/IFCjs/test-ifc-files)에서 얻으실 수 있습니다.

* IFC.js를 사용하는 것은 웹 개발(HTML, CSS, JavaScript)과 Three.js에 대한 기본 지식이 필요합니다. 만약 Three.js을 경험해 보지 않았다면 [여기](https://threejs.org/manual/)에 들어가서 보시기 바랍니다.

이 최소한의 튜토리얼은 React, Vue, Angular, Svelte 등의 프레임워크들을 사용하지 않고 바닐라 JavaScript만으로 진행이 가능합니다. 하지만 동일한 단계를 적용하여 이러한 사용 사례에 적용할 수 있습니다.

## 프로젝트 설정하기

### 라이브러리 설치하기

처음 해야 할 것은 빈 폴더를 만들고 커맨드 `npm init`으로 새로운 npm 프로젝트를 시작하십시오. 이렇게 하면 프로젝트 이름, 버전, 커맨드, 디펜던시(dependencies) 같은 몇 가지 데이터를 포함하는 `package.json` 파일이 생성될 것입니다. 또한 npm을 통해 다음 디펜던시(dependencies)를 설치해야 합니다:

```bash
// IFC.js 설치하기
npm i web-ifc-three

// Three.js 설치하기
npm i three

// 번들러(bundler) 설치하기: 저희는 이 가이드에서 rollup.js를 사용할 것입니다.
npm i rollup --save-dev
npm i @rollup/plugin-node-resolve --save-dev
```

다음 단계는 애플리케이션의 메인 문서인 `index.html` HTML 파일을 만드는 것입니다. HTML은 다음 요소들을 갖게 될 것입니다:

* **canvas 요소**: Three.js 장면을 렌더링하는 데 사용됩니다.

* **input 요소**: 컴퓨터에 있는 IFC 파일을 애플리케이션에 열 것입니다.

* `bundle.js`이라는 파일을 참조하는 **스크립트**: 이것은 rollup으로 만들게 될 앱의 번들(bundle)입니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <title>Document</title>
  </head>
  <body>
    <input type="file" name="load" id="file-input" />
    <canvas id="three-canvas"></canvas>
    <script src="bundle.js"></script>
  </body>
</html>
```

### 스타일 추가하기

다음 CSS 파일은 canvas 전체 화면을 만들 것입니다:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  overflow: hidden;
}

#three-canvas {
  position: fixed;
  top: 0;
  left: 0;
  outline: none;
}

#file-input {
  z-index: 1;
  position: absolute;
}
```

### 번들링(Bundling)

다음은 rollup 구성 파일을 만들 것입니다. 이 파일의 이름은 `rollup.config.js`이어야 합니다. 그리고 예전에 설치한 플러그인들에 대한 레퍼런스를 포함해야 합니다.

* Rollup? Rollup이란 매우 유명한 번들링 라이브러리입니다. 한 예로 Three.js가 사용하는 번들러입니다. 더 자세한 것은 [rollup 문서](https://rollupjs.org/guide/en/)를 보십시오.

```js
import resolve from "@rollup/plugin-node-resolve";

export default {
  input: "src/app.js",
  output: [
    {
      format: "esm",
      file: "src/bundle.js",
    },
  ],
  plugins: [resolve()],
};
```

또한 `package.json` 파일은 rollup을 쉽게 제어하는 커맨드들을 포함하도록 수정해야 합니다. 각 커맨드에서는 rollup 구성 파일의 상대 경로를 지정해야 합니다. 모두 제대로 설치했다면 이 파일에서 동일한 디펜던시(dependencies)를 확인해야 합니다. (라이브러리의 버전은 다를 수 있음)

* `npm run build`는 프로젝트를 번들화하고 프로젝트의 루트 디렉토리에 `bundle.js`라는 파일을 만들 것입니다.

* `npm run watch`는 `watch mode`를 활성화할 것입니다. 이 모드는 코드를 변경하고 저장할 때마다 자동으로 파일을 업데이트합니다.

```json
{
  "name": "example",
  "version": "1.0.0",
  "description": "-",
  "main": "app.js",
  "scripts": {
    "build": "rollup -c ./rollup.config.js",
    "watch": "rollup -w -c ./rollup.config.js"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "@rollup/plugin-node-resolve": "^11.2.1",
    "rollup": "^2.45.2"
  },
  "dependencies": {
    "three": "^0.128.0",
    "web-ifc-three": "0.0.102"
  }
}
```

### WebAssembly

다음 해야 할 것은 프로젝트 내 한 디렉토리에 `web-ifc.wasm`와 `web-ifc-mt.wasm` 파일을 복사하는 것입니다. 이것은 `node_modules\web-ifc`에서 찾을 수 있습니다. (또는 Three의 IFCLoader만 사용하고 있을 경우 `node_modules\three\examples\jsm\loaders\ifc`에서 찾을 수 있음) 원하는 곳에 복사할 수 있습니다; 이 예제에서는 프로젝트의 루트 디렉토리 내 wasm 폴더에 복사할 것입니다.

이 파일들은 반드시 있어야 합니다. 왜냐하면 이것은 네이티브 속도로 IFC 파일을 읽고 쓰기 위한 파싱 코어인 [web-ifc](https://github.com/IFCjs/web-ifc)의 컴파일된 C++ 로직을 포함하고 있기 때문입니다.

* 이 파일들은 애플리케이션에서 정적으로 제공되어야 합니다. React, Angular, Vue, Svelte와 같은 프레임워크나 라이브러리를 사용하고 있을 경우 다른 조정이 필요할 수도 있습니다.

## 3D 장면 설정하기

마지막으로 애플리케이션을 위한 코드를 작성하기 위해 JavaScript 파일을 만들 것입니다. 이 파일은 아무 곳에 있을 수 있으며 아무 이름을 가질 수 있습니다만 이것을 `rollup.config.js`에 반영해야 합니다.

Three.js를 이용하여 기본 3D 장면을 생성할 것입니다.

```javascript
import { AmbientLight, AxesHelper, DirectionalLight, GridHelper, PerspectiveCamera, Scene, WebGLRenderer } from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";

// Three.js 장면 생성하기
const scene = new Scene();

// 뷰포트 크기를 저장하기 위한 객체
const size = {
  width: window.innerWidth,
  height: window.innerHeight,
};

// 카메라 생성 (사용자의 관점)
const aspect = size.width / size.height;
const camera = new PerspectiveCamera(75, aspect);
camera.position.z = 15;
camera.position.y = 13;
camera.position.x = 8;

// 장면의 광원들을 생성함
const lightColor = 0xffffff;

const ambientLight = new AmbientLight(lightColor, 0.5);
scene.add(ambientLight);

const directionalLight = new DirectionalLight(lightColor, 1);
directionalLight.position.set(0, 10, 0);
directionalLight.target.position.set(-5, 0, 0);
scene.add(directionalLight);
scene.add(directionalLight.target);

// HTML의 canvas를 가져오면서 렌더러 설정하기
const threeCanvas = document.getElementById("three-canvas");
const renderer = new WebGLRenderer({
  canvas: threeCanvas,
  alpha: true,
});

renderer.setSize(size.width, size.height);
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

// 장면 내 그리드, 축 생성
const grid = new GridHelper(50, 30);
scene.add(grid);

const axes = new AxesHelper();
axes.material.depthTest = false;
axes.renderOrder = 1;
scene.add(axes);

// 궤도 제어 생성 (장면을 탐색하기 위함)
const controls = new OrbitControls(camera, threeCanvas);
controls.enableDamping = true;
controls.target.set(-2, 0, 0);

// 애니메이션 루프
const animate = () => {
  controls.update();
  renderer.render(scene, camera);
  requestAnimationFrame(animate);
};

animate();

// 뷰포트를 브라우저 크기에 맞게 조정
window.addEventListener("resize", () => {
  size.width = window.innerWidth;
  size.height = window.innerHeight;
  camera.aspect = size.width / size.height;
  camera.updateProjectionMatrix();
  renderer.setSize(size.width, size.height);
});
```

애플리케이션을 로컬에서 실행하려면 로컬 서버가 필요합니다. 만약 VS Code를 IDE로 사용 중이라면 [Live Server 확장](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)을 설치하는 옵션이 있습니다. 이것은 저희가 만든 애플리케이션을 실행해서 실시간으로 코드의 변화를 볼 수 있는 Google Chrome 인스턴스를 열 수 있게 해줍니다.

## IFC 파일 로드하기

### 사용자의 모델 로드하기

마지막으로 IFC 파일을 로드하기 위해 IFC.js를 사용할 것입니다. 이것은 로더를 인스턴스화하고 사용자가 IFC 파일을 HTML input 요소에 업로드할 때 이벤트를 생성하여 수행할 수 있습니다.

```javascript
import { IFCLoader } from "web-ifc-three/IFCLoader";

// IFC 로딩 설정
const ifcLoader = new IFCLoader();

const input = document.getElementById("file-input");
input.addEventListener(
  "change",
  (changed) => {
    const file = changed.target.files[0];
    var ifcURL = URL.createObjectURL(file);
    ifcLoader.load(ifcURL, (ifcModel) => scene.add(ifcModel));
  },
  false
);
```

만약 프로젝트의 제공된 파일들의 루트에 wasm 파일들을 저장하지 않았다면 `setWasmPath`로 해당 위치를 지정해 주어야 합니다. 예를 들어 프로젝트의 루트에 있는 `static`이라는 폴더에 포함된 `wasm`이라는 폴더에 저장했다면 다음과 같이 진행하시면 됩니다:

```javascript
ifcLoader.ifcManager.setWasmPath("static/wasm/");
```

모두 제대로 했다면, 로컬 서버에서 [이것](https://ifcjs.github.io/hello-world/examples/web-ifc-three/helloworld/)과 비슷한 뭔가를 보게 될 것입니다. 이제부터는 가능성이 무궁무진합니다.

### 모델 로드하기

앞에서는 BIM 모델을 직접 로드하는 방법을 보여 드렸습니다. 아주 훌륭했습니다. 만약 사용자가 업로드하는 것을 허용하지 않고 대신 저희의 BIM 모델들을 보여주고 싶다면? 이는 매우 간단합니다. 일반적으로 2가지 방법이 있습니다:

* 보여주고자 하는 IFC 파일을 애플리케이션과 동일한 곳에 두기.

* 보여주고자 하는 IFC 파일을 외부 저장소로부터 가져오기.

1번째의 경우 IFC 파일의 URL을 참조하는 것으로 충분합니다. 즉, 애플리케이션의 상대 경로를 이용하는 것입니다. 예를 들어, IFC 파일이 프로젝트의 루트에 있는 "models" 폴더 안에 있다면 애플리케이션을 시작할 때 다음과 같이 IFC를 로드할 수 있습니다:

```javascript
ifcLoader.load("models/Example_model.ifc", (ifcModel) => scene.add(ifcModel));
```

* 원격 저장소에서 파일을 가져오는 방법은 사용하는 서비스에 따라 달라질 수 있습니다. 그러나 로직은 동일합니다: 정보를 가져오고, URL을 생성한 후 IFCLoader에게 인자로 넘겨줍니다.

## 결론

축하합니다! 당신은 이제 1번째 IFC 뷰어를 생성했습니다. 이제 IFC.js로 당신이 할 수 있는 다른 것들을 알아보기 위해 문서의 다음 페이지로 넘어가십시오.

* IFC.js로 무엇을 할 수 있습니까? 이것은 시작에 불과합니다. 당신은 객체 선택, 지오메트리 외형 변경, 단면도 등 여러 가지 도구들을 포함하는 [web-ifc-viewer](https://github.com/IFCjs/web-ifc-viewer)를 보실 수 있습니다. [여기](https://ifcjs.github.io/web-ifc-viewer/example/index)에서 시도해 보십시오.

---

# 시작하기

## IFC.js 이해하기

IFC.js는 단순한 라이브러리가 아닙니다: 이것은 BIM 도구들을 쉽게 만들 수 있게 해주는 라이브러리 및 프로젝트의 생태계입니다. 이 모듈 방식에 대한 2가지 이유가 있습니다:

* 애플리케이션에서 필요한 것만 사용할 수 있음

* 라이브러리의 유지보수 관리성을 높이기 위함

각각의 경우에 무엇을 사용해야 하는지 알기 위해서는 어떤 조각들이 그것을 구성하는지 이해하는 것이 중요합니다. IFC.js는 기본적으로 3개의 레이어로 구성되어 있으며 각 레이어는 고유한 역할이 있습니다.

|web-ifc|
|-|
|IFC 파일 파서(parser)입니다. 이것은 IFC 파일에서 모든 정보를 읽어올 수 있으며 IFC 파일을 편집하거나 아예 새로운 IFC 파일을 만들 수도 있습니다. 이것은 3D 뷰어를 갖고 있지 않으며 단지 데이터를 다룰 뿐입니다.|
|사용하는 시기: 뷰어 없이 IFC 파일을 읽거나 쓰고 싶을 때입니다. 이 라이브러리는 데이터에 대한 모든 권한을 제공하지만 제대로 사용하려면 IFC 스키마에 대한 많은 이해도를 요구합니다.|
|다음에 의존함: -|

|web-ifc-three|
|-|
|3D BIM 뷰어입니다. 이것은 60 fps로 3D 모델을 보거나 탐색할 수 있게 해주고, 요소들을 선택하거나, IFC 데이터를 모두 읽어서 최종 사용자에게 표시해줄 수 있습니다. 이것은 three.js의 공식 IFC Loader입니다.|
|사용하는 시기: 당신의 애플리케이션을 위한 BIM 뷰어를 만들고 싶고, 구현된 모든 기능을 모두 제어하고 싶을 때입니다.|
|다음에 의존함: web-ifc|

|web-ifc-viewer|
|-|
|이미 구현된 많은 도구와 기능(단면도, 치수 등)을 갖춘 3D BIM 뷰어입니다. 조금만 수고해서 BIM 도구들을 만들 수 있게 만들었습니다.|
|사용하는 시기: BIM 뷰어를 만들고는 싶은데 당신이 원하는 모든 모델 탐색 도구들을 구현하는 데 시간을 쓰고 싶지는 않을 때입니다.|
|다음에 의존함: web-ifc-three|

---

# web-ifc

## Web-ifc 가이드

**web-ifc**는 네이티브 속도로 ifc 파일을 읽고 쓸 수 있는 자바스크립트 라이브러리입니다. **web-ifc**는 [ifc.js](https://ifcjs.github.io/info/) 프로젝트의 일부입니다. 이 프로젝트는 개방형 BIM 애플리케이션을 개발하기 위한 문턱을 낮추는 데 목적을 두고 있습니다.

### 하지만 나는 프로젝트에 대해 아무 것도 모릅니다!

걱정하지 마십시오: 만약 참여를 원하신다면 **당신의 onboarding을 최우선으로 고려하여** 당신이 라이브러리를 바로 사용할 수 있게 해주고 당신이 원하는 것으로 저희를 도우실 수 있습니다.

## 로컬에 리포지토리 클로닝(Cloning)하기

1번째로 해야 할 것은 당신의 로컬 머신에 리포지토리를 클론을 만드는 것입니다.
(우상단의 fork 버튼을 클릭하여) 프로젝트를 포크(fork)하여 시작하시고 (만약 물어본다면) 포크의 소유자를 당신 자신으로 선택하십시오.
이제 포크된 리포지토리로 가서 (일반적으로 녹색으로 된) 코드(code) 버튼을 클릭하시고 https URL을 복사하십시오.

이제 당신의 머신에서 터미널을 여시고 현재 작업 디렉토리를 복제하고 싶은 디렉토리로 변경하십시오. 다음 커맨드들을 입력하십시오:

```bash
// git clone을 타이핑하고 나서 다음과 같이 앞에서 복사한 URL을 붙여넣으세요.
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY

// 현재 디렉토리를 변경하십시오 그리고 cd를 이용하여 복제된 리포지토리를 입력하십시오. 그리고 나서 다음과 같이 리포지토리의 이름을 넣으십시오.
cd web-ifc

// git checkout -b를 이용하면 새로운 브랜치(branch)를 생성하게 되고 즉시 해당 브랜치로 전환하게 됩니다.
git checkout -b ＜new-branch-name＞
// <new-branch-name> -> 당신의 브랜치 이름은 정확하게 바운티 이름 또는 바운티 ID로 시작하는 이름과 동일해야 합니다.

// 이 터미널을 닫지 마시고 최소화하십시오.
```

## 프로젝트 설정하기

### 로컬에서 빌드

```bash
// web-ifc 설치하기
npm install web-ifc
```

## 빠른 설정

```javascript
// 현재 터미널에 있지 않을 때마다 프로젝트에서 이것을 사용하십시오.
const WebIFC = require("web-ifc/web-ifc-api.js");

// API 초기화
const ifcApi = new WebIFC.IfcAPI();

// 라이브러리 초기화
await ifcApi.Init();

// 데이터로부터 모델 열기
let modelID = ifcApi.OpenModel(/* string 또는 UInt8Array 타입으로 된 IFC 데이터 */, /* 선택적 설정 객체 */, );

// 이제 모델이 로드되었습니다! 지오메트리 또는 속성들을 가져오려면 modelID를 사용하십시오.
// IFC 읽기/쓰기에 대한 더 자세한 방법은 examples/usage를 확인하십시오.

// 모델을 닫습니다. 모든 메모리가 해제됩니다.
ifcApi.CloseModel(modelID);
```

web-ifc를 사용하는 방법을 더 자세히 알고 싶으시면 [예제](https://github.com/tomvandig/web-ifc/tree/main/examples/usage/src)를 보십시오.

## WASM 모듈 빌드하기

### emscripten 설정하기

WASM 라이브러리는 emscripten을 통해 빌드됩니다. emscripten 설정 방법에 대한 정보는 [emscripten 설치 가이드](https://emscripten.org/docs/getting_started/downloads.html)를 보십시오. 그 후에 당신의 경로(환경 변수)에 Afterwards `emsdk_env`를 추가하십시오.

### WASM 라이브러리

다시 터미널을 열어서 다음 커맨드들을 실행하십시오:

* `npm install`을 실행하여 모든 디펜던시(dependencies)를 설치하십시오.

* 새 터미널을 열 때마다 `npm run setup-env`를 실행하십시오. 이렇게 하면 코드를 컴파일하는데 필요한 emscripten 환경 변수들을 설정하게 됩니다.

* `npm run build-release-all`을 실행하여 wasm 바이너리와 web-ifc API의 릴리즈 버전을 빌드하십시오. 결과물은 ./dist에 배치될 것입니다.

* `npm run dev`를 실행하여 기본 ifc 파일 뷰어와 함께 개발 서버를 실행하십시오.

## 코드 작성하기

### IDE (Integrated Development Environment) 이용하기

VS Code - [여기](https://code.visualstudio.com/download)에서 VS Code를 설치할 수 있습니다.

### 코드를 위한 컴파일러

* GCC with MinGW (windows용) - [여기](https://code.visualstudio.com/docs/cpp/config-mingw) 설명을 따라 GCC C++ 컴파일러를 구성할 수 있습니다.

* Clang (macOS용) - [여기](https://code.visualstudio.com/docs/cpp/config-clang-mac) 설명을 따라 Clang 컴파일러를 구성할 수 있습니다.

비록 라이브러리의 기본 목적은 WebAssembly를 통해 브라우저/nodejs에서 사용되는 것이지만 이 프로젝트는 C++ 라이브러리 또는 실행파일 형태로서 독립적으로 사용될 수 있습니다. 시작하기 위한 간단한 엔트리 포인트에 대해서는 [여기](https://github.com/tomvandig/web-ifc/blob/main/src/wasm/web-ifc-test.cpp)를 보십시오.

## submit pull request 만들기

터미널을 열고 다음 커맨드들을 입력하십시오:

* 변경사항을 다시 보려면 `git status`를 사용하십시오.

* master branch를 확인하려면 `git checkout master`를 사용하십시오.

* 복제된 리포지토리를 원래 리포지토리와 동기화하려면 `git pull`을 사용하십시오.

* 작업 중인 branch로 돌아오려면 `git checkout <branch-name>`을 사용하십시오.

* main branch와 동기화하려면 `git pull`을 사용하십시오.

* 변경사항을 올리려면 `git add .`를 사용하십시오.

* 변경사항을 기록(commit)하려면 `git commit -m "type a message to display for changes"`를 사용하십시오.

* main 리포지토리로 변경사항을 업로드(push)하려면 `git push`를 사용하십시오.

이제 당신의 깃허브로 가서 리포지토리의 복제된(forked) 버전으로 들어가십시오. (pull request를 클릭하지 않았다면) 오른쪽 'compare & pull request' (일반적으로 녹색 버튼) 알림을 보게 될 것입니다. 그것을 클릭하십시오. 이제 간략하게 당신이 변경한 내용에 대한 설명을 넣고 'create pull request'를 클릭하십시오.

### 어떻게 시작하나요

[저희에게 말해보세요!](https://discord.gg/FXfyR4XrKT) 당신이 처한 상황과 당신의 아이디어를 말해주세요. 그러면 가능한 빨리 시작할 수 있도록 도와줄게요.
  
## 소개

### 네이티브 속도로 전체 IFC 제어

사람들은 웹 애플리케이션이 데스크톱 애플리케이션만큼 강력하지 않다고 흔히 생각합니다. 그러나 비교적 최근에 [WebAssembly](https://webassembly.org/)가 등장했습니다.

* WebAssembly는 웹 애플리케이션을 만들기 위해 C++과 같은 언어들을 사용하는 것을 허용하는 기술입니다.

이것은 2가지 세상의 가장 좋은 것을 얻을 수 있다는 것을 의미합니다: 웹 애플리케이션의 **유연성**과 머신의 **완전한 성능**. 그리고 이것이 web-ifc의 모든 것입니다. 당신은 `npm i web-ifc` 또는 `yarn add web-ifc`로 이것을 설치할 수 있습니다. 그리고 이것은 다음 기능들을 갖고 있습니다:

* 맨 처음부터 C++로 작성된 파싱 코어 덕분에 네이티브 애플리케이션만큼 **빠릅니다**.

* **클라이언트**에서 직접 실행하거나 **백엔드 서비스**에서 작동할 수도 있습니다. BIM을 시스템의 모든 부분으로 가져오십시오!

* **IFC 타입들을 포함한 100% IFC 데이터**를 읽을 수 있습니다. 데이터를 쉽게 추출하거나 구조화하거나 순회하거나 데이터베이스로 입력하는 것이 가능합니다.

* **IFC 데이터를 편집하거나 맨 처음부터 전체 IFC 파일을 작성**할 수 있습니다. 대형 소프트웨어 벤더들과 통신하는 앱들을 만드십시오.

이후에는 API와 그 기능들을 단계적으로 보여줄 것입니다. 그러나 `web-ifc`를 사용하기 전에 명확하게 해야 할 중대한 **몇 가지 이슈들**이 있습니다.

### 잠깐만요? 전 C++을 모르는데요!

걱정하지 마세요! 비록 파서(parser)가 C++로 작성되어 있기는 하지만 **브라우저가 자동으로 이해할 수 있는** `web-ifc.wasm` 파일로 컴파일됩니다. 당신의 애플리케이션이 이 파일을 include 시키기만 하면 **JavaScript** 또는 **TypeScript**를 이용하여 네이티브 속도로 전체 API에 접근할 수 있습니다. 대단하지 않나요?

### .wasm 파일은 무엇을 위한 것입니까?

web-ifc.wasm 파일은 IFC **파싱 코어**를 포함하고 있습니다. 이것은 미리 컴파일되어 있으며 **극도로 효율적**입니다; 한 줄씩 컴파일되는 JavaScript와 달리 이 파일은 사전 해석 없이 CPU에 직접 전송되고 실행될 수 있습니다.

`node-modules/web-ifc/web-ifc.wasm` 폴더에서 이 파일을 찾을 수 있습니다. (프론트엔드일 경우) 이 파일을 당신의 애플리케이션에 제공하거나 (백엔드일 경우) 서버에 저장해야 합니다.

* 주의사항: 당신의 애플리케이션에서 web-ifc 버전을 업데이트할 때, web-ifc.wasm의 해당 버전도 업데이트(복사)해야 합니다.

### 언제 web-ifc를 사용해야 합니까?

`Web-ifc`는 **초경량**이며 **매우 유연한 ** IFC.js의 모듈입니다. 그러나 이 유연성은 당신이 무엇을 하고 있는지 알고 있어야 하며 IFC 스키마의 내부를 비교적 잘 알고 있어야 함을 의미합니다.

게다가 web-ifc는 **3D 뷰어를 구현하지 않습니다**. 특정 3D 렌더러에 의존하지 않고도 민첩한 방식으로 IFC 지오메트리를 얻을 수 있기 때문에 이것은 오히려 장점이라고 할 수 있습니다.

* 만약 3D 지오메트리를 쉽게 보고 싶다면, 당신이 직접 구현하든가, **web-ifc-three** 또는 **web-ifc-viewer**를 이용해야 합니다.

## Hello World

## 소개

Web-ifc는 ifc 파일을 쉽게 읽고 조작하는 방법을 제공해줍니다. 예제에 나온대로 공간 트리 정보 또는 프로젝트, 지오메트리, 새로운 엔티티 추가 등이 가능합니다. 이 튜토리얼에서는 **ifc 파일 로드하기**와 **IFCSPACE로부터 모두 가져오기**를 해보겠습니다.

web-ifc 덕분에 이 모든 것이 용이합니다.

* 전체 코드는 [여기](https://github.com/ifcjs/hello-world/tree/main/examples/web-ifc/hello-world)에서 얻을 수 있습니다.

## 프로젝트 설정하기

당신의 머신에 Node JS를 반드시 설치해야 합니다. 그리고 Visual Studio Code에 Live server 플러그인을 설치하는 것을 권장합니다.

### 디펜던시(dependencies) 설치하기

```bash
npm init
npm install web-ifc
npm install rollup --save-dev
npm install @rollup/plugin-node-resolve --save-dev
npm install @open-wc/building-rollup --save-dev
```

### package.json에 스크립트 추가하기

package.json을 열고 scripts 섹션에 build와 watch라는 이름을 추가합니다.

```json
  "scripts": {
    "build": "rollup -c ./rollup.config.js",
    "watch": "rollup -w -c ./rollup.config.js"
  },
```

### Rollup 구성하기

프로젝트 루트에 구성 파일 **rollup.config.js**를 추가하십시오. 구성 파일의 내용은 다음과 같습니다:

```javascript
import resolve from "@rollup/plugin-node-resolve";

export default {
  input: "app.js",
  output: [

    {
      format: "esm",
      file: "bundle.js",
    },
  ],
  plugins: [resolve()],
};
```

## 루트 폴더를 채우십시오 :)

쉽게 하려면 루트 폴더에 다음을 모두 넣으십시오:

* app.js

* index.html

* 테스트하려고 당신이 선택한 .ifc 파일을 넣어 두십시오.

* **node_modules/web-ifc**로부터 **web-ifc-mt.wasm**과 **web-ifc.wasm**을 루트 폴더에 복사하십시오.

### 서버로부터 파일 제공하기

Visual Studio Code를 애용하는 분들을 위해 모든 고민거리를 없애줄 확장이 있습니다. 이것은 당신의 번들화된 앱을 제공하기 위한 기능을 제공해 줄 것입니다. 다른 경우에는 node 서버를 통해 코드를 직접 실행할 수 있습니다.

https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer

## 어떻게 해야 합니까?

이제 시작하기에 앞서 당신은 폴더를 갖고 있을 것입니다. 다음 2가지를 완료해 봅시다:

* ifc 파일 로드하기

* 로드된 ifc 파일로부터 데이터 가져오기

### .ifc 파일 획득하기

만약 샘플 ifcModel이 없다면 [여기](https://github.com/IFCjs/test-ifc-files)에서 하나 가져오실 수 있습니다.

### index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WEB-IFC</title>
</head>
<body>
  <div id="main">
      <div id="result"></div>
  </div>
  <script src="bundle.js"></script>
</body>
</html>
```

### app.js

#### 정의

**web-ifc/web-ifc-api**만 필요합니다. ifcFileLocation만 신경쓰시면 됩니다. 이 데모에서 루트 폴더에 저장된 ifcModel입니다.

```javascript
import {IfcAPI} from "web-ifc/web-ifc-api";
const ifcFileLocation = "duplex-apartment.ifc"; // 당신의 ifc 파일명으로 변경하는 것을 명심하세요
let modelID = 0;
const ifcapi = new IfcAPI();
ifcapi.SetWasmPath("./wasm/"); // wasm 파일이 app.js와 같은 레벨에 있는 노트일 경우에만
```

#### ifcFile 함수 가져오기

파일을 가져오기 위해 XMLHttpRequest를 선택했습니다. 당신이 원하는 아무 방식을 선택하셔도 됩니다. 마지막에 필요한 것은 `new Uint8Array(oReq.response)` 뿐입니다.

```javascript
/**
 * resolve a Uint8Array().
 * 
 * @param string ifc 파일의 url 위치
 * @returns {Promise}
 */
function getIfcFile(url) {
    return new Promise((resolve, reject) => {
        var oReq = new XMLHttpRequest();
        oReq.responseType = "arraybuffer";
        oReq.addEventListener("load", () => {
            resolve(new Uint8Array(oReq.response));
        });
        oReq.open("GET", url);
        oReq.send();
    });
}
```

#### Web-ifc로 파일 로드하기

거의 다 했습니다 ;) ifcapi가 초기화되면 ifcFile을 가져옵니다. 그리고 ifcapi를 이용해서 로드된 파일을 가지고 작업할 수 있습니다.

```javascript
ifcapi.Init().then(()=>{
  getIfcFile(ifcFileLocation).then((ifcData) => {
    modelID = ifcapi.OpenModel(ifcData);
    let isModelOpened = ifcapi.IsModelOpen(modelID);
    console.log({isModelOpened});
    ifcapi.CloseModel(modelID);
  });
});
```

#### 빌드해 봅시다.

앱을 열기 전에 커맨드 **npm run build**를 실행하십시오. rollup이 앱을 빌드할 것입니다. 그리고 나서 앱을 제공할 수 있게 됩니다. 만약 Visual Studio Code에 live server 확장이 설치되어 있다면 그저 실행해서 hello_world 예제로 갈 수 있습니다. 코드가 변경되면 다시 빌드하는 것을 잊지 마십시오. 그렇지 않으면 작업이 완료되지 전에 **npm run watch**를 사용할 수 있습니다. rollup은 코드가 저장될 때 다시 빌드할 것입니다.

콘솔에서 다음 메시지를 보게 될 것입니다. `{isModelOpened: true}`

**축하합니다**

설정이 완료되었고 실행 중입니다. 하지만 이제 **모든** IFCSPACES를 원합니다.

### 공간 목록 가져오기

자, 이제 모든 IFCSPACES를 가져와서 어딘가에 표시하고 싶습니다. 모든 IFCSPACES를 가져오는 함수를 만들어봅시다. 원하는 어떤 타입이라도 가져올 수 있습니다. 저는 IFCSPACE를 가져오기 위해 전적으로 자의적인 결정을 내렸습니다.

```javascript
/**
 * ifc 파일로부터 모든 IFCSPACE 가져오기
 * @param integer modelID 
 * @returns array
 */
function getAllSpaces(modelID) {
    // IFC 파일에 있는 모든 프로퍼티셋 라인 가져오기
    let lines = ifcapi.GetLineIDsWithType(modelID, IFCSPACE);
    let lineSize = lines.size();
    let spaces = [];
    for (let i = 0; i < lineSize; i++) {
        // 각 라인으로부터 ElementID 가져오기
        let relatedID = lines.get(i);
        // relatedID를 이용하여 요소 데이터 가져오기
        let relDefProps = ifcapi.GetLine(modelID, relatedID);
        spaces.push(relDefProps);

    }
    return spaces;
}
```

주위를 기울이면 **let lines = ifcapi.GetLineIDsWithType(modelID, IFCSPACE);**로부터 const IFCSPACE가 보일 것입니다. 이것은 ifc 파일로부터 모든 IFCSPACE를 가져온다는 것을 의미합니다. 다음과 같이 이것을 가져오는 것을 명심하십시오.

```javascript
import {IfcAPI,IFCSPACE} from "web-ifc/web-ifc-api";
```

#### getAllSpaces 호출하기

.ifc 파일을 가져온 후에 ifcapi에서 로드되면 이제 모든 공간을 가져오기 위해 나의 함수를 호출할 수 있습니다.

```javascript
ifcapi.Init().then(() => {
    getIfcFile(ifcFileLocation).then((ifcData) => {
        modelID = ifcapi.OpenModel(ifcData);
        let isModelOpened = ifcapi.IsModelOpen(modelID);
        console.log({isModelOpened});
        let spaces = getAllSpaces(modelID);
        console.log({spaces});
        ifcapi.CloseModel(modelID);
    });
});
```

## 다음 단계

**축하합니다** 이제 .ifc 파일을 로드하고 원하는 아무 요소를 찾을 수 있습니다. 그러나 공간 트리를 탐색하거나 IFCSPACE를 설명하는 것이 더 좋을 수도 있습니다... 다음에 계속

## 프로퍼티 편집하기

IFC.js는 IFC 파일을 읽고 데이터를 파싱(parse)하는 것만 하지 않습니다; web-ifc 라이브러리는 작성 기능도 갖고 있습니다. 이 멋진 기능은 사용자가 ifc 항목들을 편집하거나 생성할 수 있게 해줍니다. 이 튜토리얼에서는 IFC 파일에서 **프로퍼티 편집** 방법과 변경사항을 새로운 파일로 저장하는 방법을 찾아볼 것입니다.

이 튜토리얼은 뷰어 없이 IFC의 **프로퍼티 편집**하는 것을 도와줄 것입니다.

* [여기](https://ifcjs.github.io/hello-world/examples/web-ifc/ifc-to-json/properties/index.html)에서 배치된 최종 결과를 확인할 수 있습니다. 그리고 [여기](https://github.com/ifcjs/hello-world/tree/main/examples/web-ifc/ifc-to-json/editing-properties)에서 전체 코드를 볼 수 있습니다.

IFC scheme 내에는 여러 타입의 프로퍼티들이 있습니다. 각각은 특정 목적을 갖고 있습니다. 그리고 IFC.js는 **이 모든 것**을 가져올 수 있습니다. 모든 프로퍼티들의 목록과 그것들을 가져오는 방법은 프로퍼티 튜토리얼에 자세히 설명이 되어 있습니다.

* 네이티브 프로퍼티: 각 IFC 클래스에 적용됨.

이론은 충분합니다! 이제 다음부터 작업을 해봅시다.

## 어떻게 해야 하는가?

### 설정하기

#### web-ifc 패키지 설치하기

`npm install web-ifc`

#### 가져오기 및 글로벌 변수

wasm 파일을 루트 디렉토리나 당신이 선택한 디렉토리에 복사했는지 확인해 보십시오. setWasmPath를 호출해야 합니다.

```javascript
import {
    IfcAPI, IFCBUILDINGSTOREY
} from "web-ifc/web-ifc-api";
..

..
..
```

#### 파일 읽기

이제 파일을 읽고 [`LoadFileData()`](https://github.com/IFCjs/hello-world/blob/main/examples/web-ifc/ifc-to-json/properties/app.js#:~:text=async%20function%20LoadFile(ifcAsText))를 호출하고 IFC 데이터를 텍스트 형태로 보낼 것입니다.

```javascript
fetch("../../../../IFC/01.ifc")
  .then((response) => response.text())
  .then((data) => {
    // 파일 데이터를 LoadFileData 메소드로 보낼 것입니다
    LoadFileData(data);
  });
..
  async function LoadFileData(ifcAsText) {
    const uint8array = new TextEncoder().encode(ifcAsText);
    modelID = await OpenIfc(uint8array);
    getLevels();
    ..
}
..
```

#### 건물 층, 즉 레벨의 이름을 바꿔보기로 합시다.

먼저 건물 층 타입 또는 IFCBUILDINGSTOREY 항목을 모두 가져와야 합니다. 이 예제에서는 IFC 건물 요소 타입인 모든 항목을 가져올 것입니다. 그리고 나서 선택된 레벨을 발견했을 때 'Nivel 2'라는 Name 프로퍼티를 걸러낼 것입니다. 이제 이름을 'Level 2'로 바꾸고 해당 라인을 새로운 파일로 저장할 것입니다.

web-ifc API는 특정 타입에 대해 주어진 모델 안에서 모든 요소들의 ID를 리턴하는 GetLineIDsWithType 함수를 갖고 있습니다. 이 함수는 2가지 인자를 갖는데 모델 id와 요소 타입입니다. web-ifc API에 포함된 IFC 타입들은 enumeration으로 되어 있으며 GetLineIDsWithType 함수와 함께 사용하기 위해 반드시 가져와야 합니다.

```javascript
..

async function getLevels() {
  levels = await ifcapi.GetLineIDsWithType(modelID, IFCBUILDINGSTOREY);
  for (let i = 0; i < levels.size(); i++) {
    const lvl = ifcapi.GetLine(modelID, levels.get(i));
    if (lvl.Name.value === "Nivel 2") {
      lvl.LongName.value = "Level 2";
      ifcapi.WriteLine(modelID, lvl);
      createDownloadLink(lvl);
    }
  }
}
..

}
```

리턴된 객체 lvl은 선택한 타입(저희의 경우 IFCBUILDINGSTOREY)에 해당하는 객체 배열입니다. 이 객체는 프로퍼티들을 포함하고 있습니다. IFCBUILDINGSTOREY에 대하여 리턴된 객체의 예시는 아래에 나와 있습니다.

프로퍼티들은 각각 값들을 감싸고(nested) 있습니다. 즉, Name 프로퍼티는 해당하는 값을 리턴하지 않을 것입니다. 객체는 `type: 1, value: "Nivel 2"`을 가진 채로 리턴할 것입니다.

그래서 name 값을 리턴하기 위해 lvl.Name.value로 참조할 것입니다.

```json
{
  "expressID": 144,
  "type": 3124254112,
  "GlobalId": {
    "type": 1,
    "value": "0w984V0GL6yR4z75YWgVzB"
  },
  "OwnerHistory": {
    "type": 5,
    "value": 41
  },
  "Name": {
    "type": 1,
    "value": "Nivel 2"
  },
  "Description": null,
  "ObjectType": {
    "type": 1,
    "value": "Nivel:Nivel 1"
  },
  "ObjectPlacement": {
    "type": 5,
    "value": 143
  },
  "Representation": null,
  "LongName": {
    "type": 1,
    "value": "Level 2"
  },
  "CompositionType": {
    "type": 3,
    "value": "ELEMENT"
  },
  "Elevation": {
    "type": 4,
    "value": 3
  }
}
```

### 변경된 파일 생성하기

모든 변경사항을 처리한 후에, 새로운 파일을 생성하고 웹 페이지에 다운로드 링크를 추가할 것입니다. 그러면 사용자가 파일을 다운로드할 수 있을 것입니다.

```javascript
function createDownloadLink(lvl) {
  const data = ifcapi.ExportFileAsIFC(modelID);
  const blob = new Blob([data]);
  const file = new File([blob], "modified.ifc");
  const url = URL.createObjectURL(file);
  const link = document.createElement("a");
  link.innerText = "Download";
  link.download = "modified.ifc";
  link.setAttribute("href", url);

  document.body.appendChild(link);
}
```

## 다음 단계

축하합니다! 당신은 이제 **어떤 IFC 파일이라도 순회**할 수 있고 원하는 프로퍼티를 추축할 수 있을 것입니다.

당신은 web-ifc API를 이용하여 프로퍼티를 편집하고, 편집된 데이터를 새로운 IFC 파일에 저장할 수 있습니다.

## 프로퍼티(Properties)

당신이 할 수 있는 대단한 것들 중 하나는 IFC 파일을 순회하고 관련 정보를 가져오는 것입니다. web-ifc는 브라우저에서 IFC 파일을 읽고 쓸 수 있는 기능을 제공해 줍니다. 이 튜토리얼에서는 IFC 파일로부터 **프로퍼티 읽기**와 **프론트엔드에서 프로퍼티 출력**을 할 것입니다.

이 튜토리얼은 뷰어 없이 IFC의 **분석**을 가져오는 데 도움을 줄 것입니다.

[여기](https://ifcjs.github.io/hello-world/examples/web-ifc/ifc-to-json/properties/index.html)에서 배치된 최종 결과를 확인할 수 있고 [여기](https://github.com/ifcjs/hello-world/tree/main/examples/web-ifc/ifc-to-json/properties)에서 전체 코드를 확인할 수 있습니다.

IFC scheme에는 여러 개의 프로퍼티들이 있습니다. 각각은 특정 목적을 갖고 있습니다. 그리고 IFC.js는 **이 모든 것**을 가져올 수 있습니다. 가장 일반적인 것들 중 일부는 다음과 같습니다:

* Native 프로퍼티: 각 IFC 클래스에 해당함.

* Type 프로퍼티: 동일한 타입의 모든 요소들의 프로퍼티를 의미함. (예. 특정 타입의 모든 외피 벽들)

* Material 프로퍼티: 해당 요소의 레이어를 구성하는 모든 재질을 의미함.

* Property 세트: 사용자 정의 프로퍼티의 임의 세트. 하나 이상의 요소와 연관된 프로퍼티의 여러 세트가 있을 수 있습니다. 각 프로퍼티 세트는 서로 관련된 임의의 프로퍼티 그룹을 포함합니다.

* Quantity 세트: 참조하는 요소의 치수를 설명하는 프로퍼티 세트입니다. 지오메트리 정의로부터 요소 치수를 암시적으로 추론할 수도 있지만, 이 명시적인 설명을 사용하면 IFC 모델을 측정하는 애플리케이션을 훨씬 쉽게 만들 수 있습니다.

이제 이론은 충분합니다! 작업을 해봅시다.

## 어떻게 합니까?

### 설정하기

#### 가져오기 및 글로벌 변수

```javascript
import {
    IfcAPI, IFCRELDEFINESBYPROPERTIES
} from "web-ifc/web-ifc-api";
..
// 표 형태로 프로퍼티들을 보여줄 것입니다. FrontEnd 섹션에서 이것에 대해 이야기할 것입니다.
const table = document.createElement("table");
..
..
```

#### 파일 읽기

파일을 읽고 [`LoadFileData()`](https://github.com/IFCjs/hello-world/blob/main/examples/web-ifc/ifc-to-json/properties/app.js#:~:text=async%20function%20LoadFile(ifcAsText))를 호출할 것입니다. 그리고 IFC 데이터를 텍스트 형태로 송신할 것입니다.

```javascript
fetch("../../../../IFC/01.ifc")
  .then((response) => response.text())
  .then((data) => {
    // 이것은 파일 데이터를 LoadFileData 메소드에 보낼 것입니다.
    LoadFileData(data);
  });
```

**요소 프로퍼티를 가져오기 위해 호출될 메소드 만들기**

**요소 데이터**를 가져오기 위한 모든 코드는 그 안에 있습니다.

```javascript
function getPropertyWithExpressId(modelID=0) {
    // 만약 이전 값이 있으면 지움
    const prop = document.getElementById("properties");
    prop.innerHTML = "";
    table.innerHTML = "";

    // 사용자로부터 요소 ID를 가져오고 다음과 같이 파싱함
    const elementID = parseInt(document.getElementById("expressIDLabel").value);
    ..
    // 요소 데이터 가져오기 - 아래를 참조할 것
    ..

    // Div에 표 첨부하기
    prop.appendChild(table);
}
```

### 요소 데이터 가져오기

`GetAllLines()`는 모든 라인들을 당신에게 제공합니다. 하지만 ElementID를 따라 라인 하나를 가져오고 싶다면?

`GetLines()`는 ElementID를 알고 있으며 그것에 대한 데이터를 원할 때 사용할 수 있습니다.

#### ElementID를 통해 요소 데이터 가져오기

```javascript
// 만약 3번째 파라미터를 true라고 하면, 평평한 결과를 얻게 됨
const element = ifcapi.GetLine(modelID, elementID);

// 이제 위에서 얻은 요소의 GUID를 가져올 수 있음
const guid = element.GlobalId.value;
```

#### 하지만 요소란 무엇입니까?

모든 엔티티(Entity)는 고유한 ElementID를 가진 요소(Element)로 간주될 수 있습니다. 위의 코드를 이용하여 해당 요소 데이터에 포함된 다양한 값들을 가져올 수 있습니다. 당신이 가져올 수 있는 값과 **Frontend에서 출력**되는 값들은 다음과 같습니다.

* [GUID](https://technical.buildingsmart.org/resources/ifcimplementationguidance/ifc-guid/) : 요소의 Globally Unique Identifier

* Name - 요소에 주어진 이름

* IfcType - 요소의 타입을 참조합니다. 예. `IFCWALL`, `IFCWINDOW`

* [IfcObjectType](https://standards.buildingsmart.org/IFC/RELEASE/IFC2x3/TC1/HTML/ifckernel/lexical/ifctypeobject.htm#:~:text=IfcTypeObject&text=Definition%20from%20buildingSMART%3A%20The%20object,%2D%20specific%20%2D%20occurrence%20modeling%20paradigm.) - 타입에 대한 특정 정보를 정의합니다.

* [Tag](https://www.visualarq.com/features/collaboration/ifc/#:~:text=Tag%20feature.-,The%20IFC%20Tag,-The%20IFC%20tag) - IFC 태그 기능을 사용하면 IFC로 내보낼 때 객체에 IFC 프로퍼티를 할당할 수 있습니다.

* 그리고 **여러 가지가 있습니다**.

#### 요소 데이터 (Element Data)

지금은 `createRowInTable()`을 **무시**하십시오. 그것에 대해서는 Frontend 섹션에서 다룰 것입니다.

지금은 그저 1번째 파라미터가 Label, 2번째 파라미터가 해당 Label에 대한 값이라는 것만 기억하십시오.

```javascript
// 이제 요소의 GUID를 가져올 수 있습니다.
const guid = element.GlobalId.value;
createRowInTable("GUID", guid);

const name = element.Name.value;
createRowInTable("Name", name);

const ifcType = element.__proto__.constructor.name;
createRowInTable("IfcType", ifcType);

const type = element.ObjectType.value;
createRowInTable("Object Type", type);

const tag = element.Tag.value;
createRowInTable("Tag", tag);
```

### 요소 프로퍼티 (Element Properties)

이제 저희는 요소 데이터를 갖게 되었습니다. 저희는 이 요소로부터 프로퍼티를 가져와야 합니다. IFC가 구조화된 방식으로는 요소 데이터를 얻은 것처럼 프로퍼티를 직접 가져올 수 없습니다. 저희는 Lines라는 프로퍼티 데이터를 가져와서 저희가 원하는 ExpressID를 따라 데이터를 걸러낼 것입니다.

너무 분주할 것 같다고요? 걱정하지 마세요. web-ifc는 **네이티브 속도**로 데이터를 쉽게 가져올 수 있습니다.

#### Type을 이용하여 모든 Lines 가져오기

저희는 요소와 함께 프로퍼티와 관계가 있는 모든 `Lines`를 가져올 것입니다. 예. `IFCRELDEFINESBYPROPERTIES`

```javascript
// IFC 파일에서 모든 프로퍼티 세트 라인들을 가져옵니다.
let lines = ifcapi.GetLineIDsWithType(modelID, IFCRELDEFINESBYPROPERTIES);
```

#### 프로퍼티 세트의 ElementID 가져오기

* Lines를 가져온 후에 이것들로부터 ElementID를 가져올 것입니다. 다음에는 이 ElementID를 가지고 위에서 했던 대로 요소 데이터를 가져올 것입니다.

* 다음에는 요소 데이터를 통해 RelatedObjects를 찾아내고 만약 이 RelatedObjects 안에 프로퍼티를 찾고자 하는 ElementID가 포함되어 있다면 그것을 로컬 배열에 저장합니다.

```javascript
// 아래 배열에다가 발견한 프로퍼티 세트의 ID를 저장할 것입니다.
let propSetIds = [];
for (let i = 0; i < lines.size(); i++) {
  // Lines로부터 ElementID 가져오기
  let relatedID = lines.get(i);

  // relatedID를 이용하여 요소 데이터 가져오기
  let relDefProps = ifcapi.GetLine(modelID, relatedID);

  // 만약 관련 ID가 존재할 경우 ID 가져오기 성공 여부
  let foundElement = false;

  // RelatedObjects는 프로퍼티, 즉 객체의 배열입니다.
  // IFC가 구조화된 방식, 동일한 프로퍼티를 사용하는 엔티티가 RelatedObjects 안에 포함되어 있습니다.
  // RelatedObjects 내부를 검색해서 ElementID가 존재하는지 여부를 확인합니다.
  relDefProps.RelatedObjects.forEach((relID) => {
    if (relID.value === elementID) {
      foundElement = true;
    }
  });

  if (foundElement) {
    // 관련 ID를 발견하면 RelatingPropertyDefinition으로 이동합니다.
    // RelatingPropertyDefinition은 프로퍼티 세트의 ID를 포함합니다.
    // 그러나 이것은 배열이 아니기 때문에 !Array.isArray() 를 사용해야 합니다.
    if (!Array.isArray(relDefProps.RelatingPropertyDefinition)) {
      console.log("Found");
      let handle = relDefProps.RelatingPropertyDefinition;

      // propSetIds 배열에다가 발견한 ID를 저장함
      propSetIds.push(handle.value);
    }
  }
}
```

무거운 짐은 다 들어올렸으니 이제는 몇 가지 단계들을 반복할 것입니다.

#### 해당 ID로부터 프로퍼티 세트 가져오기

* 네, 맞습니다. 요소 ID를 이용하여 요소 데이터를 가져옵니다. 이제 propSetIds에 저장된 ID를 사용하여 데이터를 가져옵니다.

* 그리고 나서 데이터가 프로퍼티를 갖고 있는지 확인할 것입니다. 예. Nominal 값을 포함하고 있는지 확인함.

* 당신이 원한다면 프로퍼티 세트를 저장할 수 있지만, 저희의 경우 프론트엔드에서 보여줄 것이기 때문에 굳이 저장할 필요는 없습니다.

```javascript
// 해당 ID로부터 프로퍼티 세트 가져오기
let propsets = propSetIds.map((id) => ifcapi.GetLine(modelID, id, true));

propsets.forEach((set) => {
  // 여러 개의 프로퍼티 세트가 있을 수 있습니다.
  set.HasProperties.forEach((p) => {
    // 값이 존재하고 null아닌지 여부를 확인할 것입니다..
    if (p.NominalValue != null) {
      // 이것은 예제 필터입니다. 결과를 변경하기 위해 다양한 조건들을 아래에 기입할 수 있습니다.
      if (p.NominalValue.label === "IFCBOOLEAN") {
        // Frontend 파트에서 이 함수에 대해 이야기할 것입니다.
        createRowInTable(p.Name.value, p.NominalValue.value);
      } else {
        // Frontend 파트에서 이 함수에 대해 이야기할 것입니다.
        createRowInTable(p.NominalValue.label, p.NominalValue.value);
      }
    }
  });
});
```

* 지금까지의 전체 코드는 [이것](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc/ifc-to-json/properties/app.js)과 같아야 합니다.

### 프론트엔드 (FrontEnd)

* 이 예제를 [기반](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc/ifc-to-json/frontend)으로 사용할 것입니다. 그리고 여기에 추가로 덧붙일 것입니다.

**행(Rows)을 생성하기 위한 메소드**: 저희는 행(rows)을 동적으로 만드는 함수를 만들 것입니다. 이것은 표에 데이터를 직접 삽입할 수 있도록 도와주고 프론트엔드에 그것을 보여줄 것입니다.

* 이제 설정을 하는 동안 저희가 글로벌하게 생성한 `table` 변수를 사용할 것입니다.

```javascript
function createRowInTable(label, value) {
  // 새로운 행(Row) 요소 생성하기
  const row = document.createElement("tr");

  // 1번째 열(Column)에 라벨을, 2번째 열에 값을 추가함
  row.innerHTML = "<td>" + label + "</td><td>" + value + "</td>";

  // 표에 행 추가하기 - 표 내부에 행을 추가하는 것을 의미함
  table.appendChild(row);
}
```

#### <body> 내부의 당신의 HTML 코드는 다음과 같아야 함

```html
<div class="file-opener">
  <a class="invisible" id="save-button">Save JSON</a>
  <button class="basic-button" id="file-opener-button">Open IFC</button>
</div>
<input class="invisible" id="file-input" type="file" />
<div class="general-container">
  <div class="container" id="left-container"></div>
  <div class="separator"></div>
  <div class="container" id="right-container">
    <div class="ifc-container">
      <pre id="json"></pre>
    </div>
    <div class="property-container">
      <div class="input-container">
        <input id="expressIDLabel" />
        <!-- 이 버튼을 클릭할 시 getPropertyWithExpressId()를 호출함 -->
        <button class="property-button" onclick="getPropertyWithExpressId()">Get Properties</button>
      </div>
      <!-- 이것은 프로퍼티들을 표시할 영역임 -->
      <pre id="properties"></pre>
    </div>
  </div>
</div>
```

#### 스타일링

컨테이너:

```css
.ifc-container {
  height: 60%;
  border-bottom: 5px solid #f3f4f6;
  overflow: auto;
}
.property-container {
  overflow: auto;
  height: 40%;
}
.input-container {
  padding: 20px;
  border-bottom: 5px solid #f3f4f6;
}
#properties {
  padding: 8px;
}
```

입력 필드 및 버튼:

```css
input {
  font-size: 14px;
  padding: 4px;
  width: 60%;
  border-radius: 8px;
}
.property-button {
  margin-left: 20px;
  font-size: 14px;
  padding: 8px 12px;
  background-color: #e6e6e6;
  border: unset;
  border-radius: 8px;
}
.property-button:hover {
  box-shadow: 0 10px 20px 8px #e6e6e6;
  background-color: white;
  transition: 0.2s;
}
```

표(Table) 및 행(Row):

```css
table {
  width: 100%;
  border-collapse: collapse;
}
tr:nth-child(even) {
  background-color: #f2f2f2;
}
td {
  border: 1px solid black;
  padding: 8px;
}
```

## 다음 단계

축하합니다! 이제 당신은 **어떤 IFC 파일이라고 순회**할 수 있으며 당신이 찾고자 하는 프로퍼티를 추축할 수 있을 것입니다.

web-ifc API를 이용하여 재질 데이터도 가져올 수 있으며 당신이 원하는 대로 라인들을 쿼리해서 더 많은 것들을 가져올 수도 있습니다.

## web-ifc-API

API는 문서화되어 있으므로 이 문서에 나열된 객체 또는 메소드를 사용할 때 당신이 사용하는 IDE가 무엇이든지 관계없이 IntelliSense로부터 도움을 받아야 합니다.

IntelliSense 또는 코멘트로는 편안하지 않을 것입니다. 이 페이지에서는 API가 할 수 있는 것이 무엇인지에 대한 개요를 보여줄 것입니다. 저희는 아래의 특정 튜토리얼 섹션에서 자세히 동작하는 것을 볼 수 있을 것입니다.

## IfcAPI

라이브러리로부터 객체를 가져옵니다. 여기서는 `FileReader`를 사용할 것입니다. 이것은 웹 애플리케이션이 파일 또는 데이터를 읽을 수 있는 File 또는 Blob 객체를 이용하여 사용자 컴퓨터에 저장된 파일(또는 raw 데이터 버퍼)의 내용을 비동기적으로 읽을 수 있게 해줍니다.

```javascript
import { IfcAPI } from "web-ifc/web-ifc-api";

const IfcAPI = new IfcAPI();
IfcAPI.SetWasmPath("../../../../");

const input = document.getElementById("file-input");
IfcAPI.Init();
input.addEventListener("change", (changed) => {
  const reader = new FileReader();
  reader.onload = () => LoadFile(reader.result);
  reader.readAsText(changed.target.files[0]);
});

async function LoadFile(ifcAsText) {
  const uint8array = new TextEncoder().encode(ifcAsText);
  const modelID = await OpenIfc(uint8array);
  const allItems = GetAllItems(modelID);
  const result = JSON.stringify(allItems, undefined, 2);
}

async function OpenIfc(ifcAsText) {
  await IfcAPI.Init();
  return IfcAPI.OpenModel(ifcAsText);
}

function GetAllItems(modelID, excludeGeometry = false) {
  const allItems = {};
  const lines = IfcAPI.GetAllLines(modelID);
  getAllItemsFromLines(modelID, lines, allItems, excludeGeometry);
  return allItems;
}

function getAllItemsFromLines(modelID, lines, allItems, excludeGeometry) {
  for (let i = 1; i <= lines.size(); i++) {
    try {
      saveProperties(modelID, lines, allItems, excludeGeometry, i);
    } catch (e) {
      console.log(e);
    }
  }
}

function saveProperties(modelID, lines, allItems, excludeGeometry, index) {
  const itemID = lines.get(index);
  const props = IfcAPI.GetLine(modelID, itemID);
  props.type = props.__proto__.constructor.name;
  if (!excludeGeometry || !geometryTypes.has(props.type)) {
    allItems[itemID] = props;
  }
}
```

ifc 파일을 로드하고 그것의 모든 정보를 평문(plain text) 형태로 리턴합니다.

```javascript
const properties = IfcAPI.properties;
```

IfcAPI 클래스는 `properties`라고 불리는 프로퍼티를 포함하고 있습니다. 이것은 `properties`, `psets`, `qsets` 등에 대한 모든 로직과 메소드를 포함하고 있습니다.

## 설정

### setWasmPath

```javascript
IfcAPI.setWasmPath("../../../../");
```

web-ifc.wasm과 web-ifc-mt.wasm 파일의 위치를 지정합니다. 이 파일들은 IFC.js로 애플리케이션을 빌드할 때 반드시 있어야 합니다. node_modules/web-ifc/에서 발견할 수 있습니다.

* 당신이 사용하는 도구를 유의하십시오!! 만약 당신이 React, Angular, Vue 또는 Svelte 같은 프레임워크나 라이브러리를 사용한다면 프로젝트의 루트 경로가 제공된 애플리케이션의 루트 경로와 일치하지 않을 수 있습니다. 정적으로 제공되는 파일의 경로가 어떻게 관리되고 있는지 [각 경우](https://github.com/IFCjs/examples)에 대해 확인해야 합니다.

#### 인자:

* path: `web-ifc.wasm`의 경로.

## 도구

### Init

```javascript
IfcAPI.init(customLocateFileHandler: LocateFileHandlerFn)
```

#### 인자:

* `customLocateFileHandler`: wasm 모듈이 로드되는 경로를 재지정할 수 있는 선택적인 locateFile 함수입니다.

#### 예제:

```javascript
IfcAPI.Init();
```

다른 기능을 사용하기 전에 반드시 있어야 하는 WASM 모듈 `WebIFCWasm`을 초기화합니다.

### OpenModel

```javascript
IfcAPI.openModel(data: Uint8Array,
                 settings: LoaderSettings): number
```

#### 인자:

* `data`: IFC `data`를 포함하는 버퍼입니다.

* `settings`: 모델을 로딩하기 위한 `settings`입니다.

#### 예제:

```javascript
IfcAPI.OpenModel(data, { LoaderSettings });
```

하나의 모델을 열고 `modelID` 번호를 리턴합니다.

### CreateModel

```javascript
IfcAPI.CreateModel(settings: LoaderSettings): number
```

#### 인자:

* `settings`: 새로운 모델을 생성하고 `modelID` 번호를 리턴합니다.

#### Example:

```javascript
IfcAPI.CreateModel();
```

새로운 모델을 생성하고 `modelID` 번호를 리턴합니다.

### ExportFileAsIFC

```javascript
IfcAPI.ExportFileAsIFC(modelID: number): Uint8Array
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다. 모델은 닫히면 안 됩니다.

#### 예제:

```javascript
IfcAPI.ExportFileAsIFC(modelID);
```

`modelID`를 이용하여 IFC 파일로 내보냅니다. `Uint8Array`를 리턴합니다.

### CreateIfcGuidToExpressIdMapping

```javascript
IfcAPI.CreateIfcGuidToExpressIdMapping(modelID: number)
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

#### 예제:

```javascript
const expressIdMapping = IfcAPI.CreateIfcGuidToExpressIdMapping(modelID);
```

요소 ExpressID와 GlobalID 간의 맵을 생성합니다. 각 요소는 2개의 엔트리를 가지고 있습니다. (ExpressID -> GlobalID)와 (GlobalID -> ExpressID)

### CloseModel

```javascript
IfcAPI.CloseModel(modelID: number)
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다. 모델은 닫히면 안 됩니다.

#### 예제:

```javascript
IfcAPI.CloseModel(modelID);
```

하나의 모델을 닫고 관련된 모든 메모리를 해제합니다.

### IsModelOpen

```javascript
IfcAPI.IsModelOpen(modelID: number): boolean
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

#### 인자:

```javascript
IfcAPI.IsModelOpen(modelID);
```

지정한 모델 ID가 열려 있는지, 닫혀 있는지 확인합니다.

### LoadAllGeometry

```javascript
IfcAPI.LoadAllGeometry(modelID: number): Vector
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

#### 예제:

```javascript
IfcAPI.LoadAllGeometry(modelID);
```

단일 요소에 대한 지오메트리를 로드합니다.

### SetGeometryTransformation

```javascript
IfcAPI.SetGeometryTransformation(modelID: number,
                                  transformationMatrix: Array)
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

* `transformationMatrix` : transformation을 인코드하려면 `transformationMatrix`를 이용하십시오.

#### 예제:

```javascript
IfcAPI.SetGeometryTransformation(modelID, transformationMatrix);
```

`modelID`와 `transformationMatrix`를 이용하여 지오메트리의 transformation을 구성합니다.

### StreamAllMeshes

```javascript
IfcAPI.StreamAllMeshes(modelID: number,
                      meshCallback:(mesh: FlatMesh))
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

* `meshCallback`: `mesh`를 이용하십시오.

#### 예제:

```javascript
IfcAPI.StreamAllMeshes(modelID, (mesh) => {});
```

`modelID`와 `messCallback`을 통해 모든 `meshes`를 수집합니다.

### StreamAllMeshesWithTypes

```javascript
IfcAPI.StreamAllMeshesWithTypes(modelID: number, types: Array<number>,
                            meshCallback:(mesh: FlatMesh))
```

#### 인자:

* modelID: `OpenModel`로 가져온 모델 핸들입니다. 모델은 닫히면 안 됩니다.

* `types` : `Array`의 `type`을 선택하십시오.

* `meshCallback`: `mesh`를 이용하십시오.

#### 예제:

```javascript
IfcAPI.StreamAllMeshesWithTypes(modelID, types, meshCallback);
```

`type`을 이용하여 `modelID`와 `messCallback`을 통해 모든 `meshes`를 수집합니다.

### WriteLine

```javascript
IfcAPI.WriteLine(modelID: number, lineObject: any)
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

* `lineObject`: 모델에서 선택된 `lineObject`입니다.

#### 예제:

```javascript
IfcAPI.WriteLine(modelID, lineObject);
```

`modelID`와 `lineObject`를 이용하여 라인 하나를 작성합니다.

### WriteRawLineData

```javascript
IfcAPI.WriteRawLineData(modelID: number, data: RawLineData)
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

* `data` : 각 라인의 raw `data`입니다.

#### 예제:

```javascript
IfcAPI.WriteRawLineData(modelID);
```

`modelID`와 `data`를 이용하여 라인 데이터를 작성합니다.

## Get

### GetAllLines

```javascript
IfcAPI.GetAllLines(modelID: Number): Vector
```

#### 인자:

* `modelID`: 모델의 Express ID입니다.

#### 예제:

```javascript
IfcAPI.GetAllLines(modelID);
```

modelID를 통해 한 모델의 모든 라인들을 가져옵니다.

### GetAndClearErrors

```javascript
IfcAPI.GetAndClearErrors(modelID: number): Vector
```

#### 인자:

`modelID`: 모델의 Express ID입니다.

#### 예제:

```javascript
return IfcAPI.GetAndClearErrors(modelID);
```

`modelID`를 이용하여 오류들을 가져오고 모두 지웁니다.

### GetCoordinationMatrix

```javascript
IfcAPI.GetCoordinationMatrix(modelID: number): Array
```

#### 인자:

* `modelID`: 모델의 Express ID입니다.

#### 예제:

```javascript
IfcAPI.GetCoordinationMatrix(modelID);
```

`modelID`를 이용하여 행렬의 좌표를 가져옵니다.

### GetFlatMesh

```javascript
IfcAPI.GetFlatMesh(modelID: number, expressID: number): FlatMesh
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

* `expressID`: 모델의 `expressID`입니다.

#### 예제:

```javascript
IfcAPI.GetFlatMesh(modelID, expressID);
```

단일 요소에 대한 지오메트리를 로드합니다.

### GetGeometry

```javascript
IfcAPI.GetGeometry(modelID: number, geometryExpressID: number): IfcGeometry
```

#### 인자:

* `modelID`: ifcModel의 `expressID`입니다.

* `geometryExpressID`: ifcModel 내 지오메트리의 `expressID`입니다.

#### 예제:

```javascript
const geometry = IfcAPI.GetGeometry(modelID, geometryExpressID);
```

`modelID`를 이용하여 `mesh` 지오메트리를 가져옵니다.

### GetIndexArray

```javascript
IfcAPI.GetIndexArray(ptr: number, size: number): Uint32Array
```

#### 인자:

* `ptr`: get의 파라미터입니다.

* `size`: `size`를 세트합니다.

#### 예제:

```javascript
IfcAPI.GetIndexArray();
```

`ptr`과 `size`를 이용하여 `Array`의 `index`를 가져옵니다.

### GetLine

```javascript
IfcAPI.GetLine(modelID: number, expressID; number,
                flatten: boolean)
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

* `expressID`: 모델의 `expressID`입니다.

* `flatten`: `flatten`인지 아닌지 여부를 세트합니다.

#### 예제:

```javascript
const props = IfcAPI.GetLine(modelID, id, (flatten = false));
```

modelID와 expressID를 이용하여 라인을 가져옵니다.

### GetLineIdsWithType

```javascript
IfcAPI.GetLineIdsWithType(modelId: number, type: number): Vector
```

#### 인자:

* `modelID`: ifcModel의 `expressID`입니다.

* `type`: 가져올 `type`을 세트합니다.

#### 예제:

```javascript
const lines = IfcAPI.GetLineIDsWithType(modelID, type);
```

가져올 타입을 정의합니다.

### GetRawLineData#

```javascript
IfcAPI.GetRawLineData(modelID: number, expressID: number): RawLineData
```

#### 인자:

* `modelID`: `OpenModel`로 가져온 모델 핸들입니다.

* `expressID`: 모델의 `expressID`입니다.

#### 예제:

```javascript
const rawLineData = IfcAPI.GetRawLineData(modelID, expressID);
```

`modelID`와 `expressID`를 이용하여 raw 데이터의 라인 하나를 가져옵니다.

### getSubArray

```javascript
IfcAPI.getSubArray(heap: any, startPtr: any,
                    sizeBytes: any)
```

#### 인자:

* `heap`: `heap`을 세트합니다.

* `startPtr`: `subArray` 안의 `startPtr`을 세트합니다.

* `sizeBytes`: `sizeBytes`를 세트합니다.

#### 예제:

```javascript
const subArray = IfcAPI.getSubArray(heap, startPtr, sizeBytes);
```

`Array` 안에서 `subArray`를 가져옵니다.

### GetVertexArray

```javascript
IfcAPI.GetVertexArray(ptr: number, size: number): Float32Array
```

#### 인자:

* `ptr`: 가져올 파라미터를 세트합니다.

* `size`: `size`를 세트합니다.

#### 예제:

```javascript
const vertexArray = IfcAPI.GetVertexArray(ptr, size);
```

`Array`의 `vertex`를 가져옵니다.

---

# web-ifc-three

## 소개

...하지만 지오메트리를 갖고 있습니다.

[Web-ifc](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/%22https://ifcjs.github.io/info/docs/Guide/web-ifc/Introduction%22)는 거의 네이티브 속도로 IFC를 읽고 쓸 수 있는 매우 강력한 도구입니다. 그러나 거의 모든 BIM 애플리케이션들은 사용자에게 작업 중인 모델의 3D 뷰를 보여줍니다. 당신은 아무 그래픽 엔진에서나 `web-ifc`를 이용할 수 있습니다만 당신을 위해 이미 **web-ifc-three** 안에 만들어 두었습니다.

`web-ifc-three`는 IFC 파일의 모든 데이터를 읽는 `web-ifc`의 랩퍼(wrapper)입니다. 그리고 브라우저에서 보고 편집할 수 있도록 데이터를 지오메트리로 변환합니다. `npm i web-ifc-three` 또는 `yarn add web-ifc-three`를 이용해 설치할 수 있습니다. 이 모듈에 대한 몇 가지 멋있는 사실들이 있습니다:

* 사용하는 것이 매우 편합니다.

* [Three.js의 공식 IFCLoader](https://threejs.org/examples/webgl_loader_ifc.html)입니다.

* 이것은 브라우저에서 60 fps로 수천 개의 객체들을 표시할 수 있어서 매우 효율적입니다. 여러 개의 모델들을 표시하거나 재질을 변경하고 항목들을 걸러낼 수 있습니다.

* 여러 개의 파일의 공간 구조 트리(spatial structure tree)를 가져오고 순회할 수 있습니다. 또, 3D 뷰에서 객체를 클릭하거나 스마트 필터를 이용해서 모든 항목의 프로퍼티에 접근할 수 있습니다.

이후에 API와 기능들에 대해 단계적으로 보여줄 것입니다. 그러나 web-ifc-three를 이용하기 전에 명확하게 해야 할 몇 가지 중요한 것들이 있습니다.

### `web-ifc`를 직접 사용할 수 있습니까?

web-ifc를 이용하면 IFC를 읽고 쓸 수 있는 대부분의 BIM 도구를 빌드할 수 있습니다. 그런데 왜 굳이 그 위에 레이어를 하나 더 만듭니까?

대부분의 BIM 도구들은 3D이기 때문에 개발자들이 맨 처음부터 뷰어를 구현하는 것은 어리석다고 생각합니다. 만약 당신이 데이터에만 관심이 있다면 web-ifc를 직접 사용하는 것이 더 나을 것입니다.

게다가 web-ifc-three는 IFC 포맷에 대한 경험이 없는 개발자라도 IFC를 가지고 쉽고 안전하게 작업할 수 있도록 도와줍니다.

* Web-ifc는 훨씬 유연하지만 IFC 스키마에 대한 지식과 더 많은 구현 노력을 필요로 합니다.

### `THREE.IFCLoader`를 직접 사용할 수 있습니까?

위에서 언급한 대로, `web-ifc-three`는 Three.js의 공식 IFCLoader입니다. 즉, 당신이 Three.js로부터 IFCLoader를 가져오면 이 코드는 `web-ifc-three` 리포지토리에서 찾게 될 코드와 같다는 것입니다.

프로젝트엣 `web-ifc-three`를 가져오지 않고 Three.js에서 `IFCLoader`를 가져올 수도 있습니다. 물론 작동하기는 하지만 Three.js는 매우 큰 라이브러리이며 업데이트 속도는 IFC.js보다 많이 느립니다.

* 약간의 지연: Three.js IFCLoader는 최신 업데이트가 없을 수도 있습니다. 그리고 저희가 수정한 최근 버그가 Three.js에서는 다음 버전이 출시될 때까지 해결되지 않은 채로 남아 있을 것입니다.

본래 `IFCLoader` 대신 `THREE.IFCLoader`를 사용하려면 import 구문만 변경하면 됩니다:

```javascript
// 원래 web-ifc-three  IFCLoader 가져오기
import { IFCLoader } from "web-ifc-three/IFCLoader";

// three.js IFCLoader 가져오기
import { IFCLoader } from "three/examples/jsm/loaders/IFCLoader";
```

## 설정

### DRY (Don't Repeat Yourself) 문서

저희는 [우리 자신을 반복](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)하고 싶지 않습니다; 심지어 저희 문서에서도 그렇습니다.

web-ifc를 이용하여 프로젝트를 시작하기 위한 설정은 이미 [Hello World](https://ifcjs.github.io/info/docs/Hello%20world)에서 보여 드렸습니다. 그 부분을 건너뛰었다면 거기로 가서 살펴 보시길 권해 드립니다. 모든 튜토리얼은 거기서부터 시작됩니다.

* 당신이 Three.js IFCLoader를 대신 사용하고 있다면 이 튜토리얼을 굳이 따르지 않아도 됩니다.

만약 튜토리얼 중에 길을 잃었다면 걱정하지 마십시오! [여기](https://github.com/IFCjs/hello-world) 예제를 보시거나 [디스코드 채널](https://discord.gg/g7Uzn2KSwB)에 오셔서 직접 물어보시면 됩니다. 또 이 문서에서 개선해야 할 점을 가르쳐 주십시오.

* 진행하기에 앞서: Three.js와 웹 개발에 대한 기본적인 지식이 있다고 가정하겠습니다. 만약 이러한 배경이 없다면 IFC.js로 넘어가기 전에 [여기](https://threejs.org/manual/)부터 시작하는 것을 권해 드립니다.

## API

모든 API는 문서화되었습니다. 그래서 당신이 이 문서에 나와 있는 객체나 메소드 중에서 사용할 때 당신이 어떤 IDE를 사용하든지 간에 IntelliSense의 도움을 받으셔야 합니다. [이것을 확인해 보십시오!](https://github.com/IFCjs/web-ifc-three/blob/main/web-ifc-three/src/IFC/components/IFCManager.ts)

IntelliSense 또는 코멘트로는 편안하지 않을 것입니다. 이 페이지에서는 API가 할 수 있는 것이 무엇인지에 대한 개요를 보여줄 것입니다. 모든 것은 나중에 나오는 구체적인 튜토리얼에서 자세히 다룰 것입니다.

### IfcLoader

저희가 라이브러리로부터 가져오게 될 유일한 객체입니다. 이것은 IFC를 가지고 작업하는 데 필요한 모든 로직을 포함하고 있습니다. [다른 Three.js Loader처럼](https://threejs.org/docs/#api/en/loaders/Loader.load) URL로부터 IFC를 로드하기 위해 `load()`와 `loadAsync()` 메소드를 사용할 수 있습니다. 예를 들어 IFC를 로드하기 위해 다음과 같이 할 수 있습니다:

```javascript
import { IFCLoader } from "web-ifc-three/IFCLoader";

const ifcLoader = new IFCLoader();
ifcLoader.load("models/Example_model.ifc", (ifcModel) => scene.add(ifcModel));
```

`web-ifc-three`를 이용하여 장면 안에 여러 개의 모델들을 로드할 수 있습니다. 많은 API 동작들이 지정한 모델에서 실행됩니다. 동작하고 싶은 모델을 표현하려면 `ModelID`를 주어야 합니다.

프로퍼티 `modelID`를 통해 모델의 ID를 가져올 수 있습니다.

```javascript
const modelID = ifcModel.modelID;
```

API에 접근하는 2가지 방식이 있습니다:

* `IfcLoader`가 `load` 및 `loadAsync`를 통해 생성하는 `IfcModel`의 인스턴스를 통해 접근할 수 있습니다.

* `IfcLoader.IfcManager`를 통해 접근할 수 있습니다.

* **IfcModel** 인스턴스와 **IfcLoader.IfcManager** 모두 API에 접근하기 위해 번갈아가며 사용할 수 있습니다. 한 가지 차이점이 있습니다: **IfcModel**을 사용할 때에는 ModelID가 인자로 주어지지 않습니다. (암묵적으로 알고 있음)

## 설정

### setWasmPath

```javascript
async IfcLoader.IfcManager.setWasmPath (
                        path: string
                        ): void;
```

`web-ifc.wasm`과 `web-ifc-mt.wasm` 파일의 위치를 지정합니다. 이 파일들은 web-ifc 파일이며 IFC.js로 애플리케이션을 만들 때 반드시 필요합니다. `node_modules/web-ifc/`에서 발견할 수 있습니다.

* 당신이 사용하는 도구를 유의하십시오!! 만약 당신이 React, Angular, Vue 또는 Svelte 같은 프레임워크나 라이브러리를 사용한다면 프로젝트의 루트 경로가 제공된 애플리케이션의 루트 경로와 일치하지 않을 수 있습니다. 정적으로 제공되는 파일의 경로가 어떻게 관리되고 있는지 [각 경우](https://github.com/IFCjs/examples)에 대해 확인해야 합니다.

#### 인자:

* `path` `web-ifc.wasm`의 경로.

#### 예제:

만약 `web-ifc.wasm`이 dist/wasmDir 안에 있다면:

```javascript
await ifcLoader.ifcManager.setWasmPath("dist/wasmDir/");
```

### setupThreeMeshBVH

```javascript
IfcLoader.IfcManager.setupThreeMeshBVH (
                        computeBoundsTree: any,
                        disposeBoundsTree: any,
                        acceleratedRaycast: any
                        ): void;
```

이 메소드는 객체 피킹(picking)을 훨씬 빠르게 해줍니다. 특히 무거운 지오메트리를 가진 초대형 모델의 경우에 그렇습니다. 이 메소드는 실제로 IFC.js가 Garrett Johnson의 놀라운 [라이브러리](https://github.com/gkjohnson/three-mesh-bvh)를 사용할 수 있게 해줍니다. `npm i three-mesh-bvh` 또는 `yarn add three-mesh-bvh`로 설치할 수 있습니다.

* 이 메소드를 사용하는 것은 의무가 아니지만, 중대형 IFC 모델에서 60 fps로 객체를 선택하고 싶으면 필수로 사용해야 합니다.

#### 인자:

* `computeBoundsTree` 이것은 새로운 BVH를 빌드하고, 그것을 boundsTree에 할당하고, 지오메트리에 새로운 인덱스 버퍼를 적용하는 미리 만들어진 BufferGeometry 확장 함수입니다. - [소스](https://github.com/gkjohnson/three-mesh-bvh#computeboundstree)

* `disposeBoundsTree` 이것은 BVH를 폐기하는 BufferGeometry 확장 함수입니다. - [소스](https://github.com/gkjohnson/three-mesh-bvh#disposeboundstree)

* `acceleratedRaycast` 이것은 THREE.Mesh.raycast와 동일한 시그니처를 가진 가속 raycast 함수입니다. 가능한 경우에는 raycasting에 BVH를 사용하지만, 그렇지 않을 경우 빌드-인 방식으로 돌아가게 됩니다. - [소스](https://github.com/gkjohnson/three-mesh-bvh#acceleratedraycast)

#### 예제:

```javascript
import { IFCLoader } from "web-ifc-three/dist/IFCLoader";

import { acceleratedRaycast, computeBoundsTree, disposeBoundsTree } from "three-mesh-bvh";

const ifcLoader = new IFCLoader();
ifcLoader.ifcManager.setupThreeMeshBVH(acceleratedRaycast, computeBoundsTree, disposeBoundsTree);
```

### setOnProgress

```javascript
IfcLoader.IfcManager.setOnProgress (
      onProgress: (event: ParserProgress) => void
                                    ): void;
```

IFC가 10%씩 로드될 때마다 호출되는 콜백 함수를 세트합니다. 이런 식으로 사용자에게 로딩 진행 상태를 보여주기 위해 로딩 바를 표시할 수 있습니다.

#### 인자:

* `onProgress`: 매 10%마다 호출되는 콜백 함수입니다. 이 함수는 2개의 프로퍼티를 가진 1개의 객체를 수신하는 하나의 인자를 가져야 합니다: (로드된 객체의 개수를 의미하는) `loaded`와 (파일 내 객체의 개수를 의미하는) `total`.

#### 예제:

```javascript
function exampleCallback(event) {
  const progress = (event.total / event.progress) * 100;
  console.log("Progress: ", progress, "%");
}

ifcLoader.ifcManager.setOnProgress(exampleCallback);
```

### applyWebIfcConfig

```javascript
async IfcLoader.IfcManager.applyWebIfcConfig (
                                    settings: LoaderSettings
                                    ): void;
```

이 라이브러리가 내부적으로 사용하는 파서(parser)인 [web-ifc](https://ifcjs.github.io/info/docs/Guide/web-ifc/Introduction)에 대한 구성을 적용합니다.

#### 인자:

* `settings`: 다음 필드들을 포함하는 객체입니다:

  * `COORDINATE_TO_ORIGIN: boolean`: 장면의 중심에 모델을 가져다 놓을지 여부를 의미합니다. 지리적 위치를 가진 모델에 유용합니다.

  * `USE_FAST_BOOLS: boolean`: 더 빠른 (그리고 덜 정확한) 불리언 로직을 사용할지 여부를 의미합니다.

  * `BOOL_ABORT_THRESHOLD?: number`: 불리언 연산 계산에 대한 한계입니다.

  * `CIRCLE_SEGMENTS_LOW?: number`: 낮은 세그먼트 곡선에 대한 해상도입니다.

  * `CIRCLE_SEGMENTS_MEDIUM?: number`: 중간 세그먼트 곡선에 대한 해상도입니다. (예. IfcSweptDiskSolid)

  * `CIRCLE_SEGMENTS_HIGH?: number`: 높은 세그먼트 곡선에 대한 해상도입니다. (예. IfcCircle)

#### 예제:

만약 파일이 지리적 위치를 가지고 있으며 장면의 원점에 그것을 가져오고 싶다면:

```javascript
await ifcLoader.ifcManager.applyWebIfcConfig({
  COORDINATE_TO_ORIGIN: true,
  USE_FAST_BOOLS: false,
});
```

### useWebworkers

```javascript
async IfcLoader.IfcManager.useWebWorkers (
                                    active: boolean,
                                    path?: string
                                    ): void;
```

파싱 로직을 포함하는 웹 작업자로 전환합니다. 나머지 API는 동일하지만 모든 로직은 머신의 다른 스레드에서 발생하므로 앱은 과도한 연산 때문에 차단되지 않을 것입니다.

당신은 파일 `IFCWorker.js`를 당신의 프로젝트에 복사하고 상대 경로를 2번째 인자로 넘겨주어야 합니다.

#### 인자:

* `active`: 웹 작업자를 사용할지 여부를 의미합니다.

* `path`: 작업자 파일에 대한 상대 경로입니다. 만약 `active = true`이면 필수입니다.

#### 예제:

만약 파일 `IFCWorker.js`가 `files`라는 폴더 안에 있을 경우:

```javascript
await ifcLoader.ifcManager.useWebWorkers({
                                true,
                                "files/IFCWorker.js"
                                            });
```

### useJSONData

```javascript
async IfcLoader.IfcManager.useJSONData (
                                    useJSON: boolean
                                    ): void;
```

메모리 사용량이 적은 WASM 데이터 대신 JSON 프로퍼티 데이터를 사용합니다. 이것은 다음 시나리오를 따를 때에만 사용하십시오:

* IFC의 프로퍼티에 접근할 필요가 없을 경우

* 프로퍼티를 JSON 형태로 제공해야 할 경우. [이 예제](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc/ifc-to-json/node)처럼 IFC 파일에서 JSON을 가져올 수 있습니다.

#### 인자:

* `useJSON`: JSON 데이터를 사용할지 여부를 의미합니다.

#### 예제:

```javascript
await ifcLoader.ifcManager.useJSONData(true);
```

### addModelJSONData#

```javascript
async IfcLoader.IfcManager.addModelJSONData (
                                modelID: number,
                                data: { [id: number]: JSONObject
                                        ): void;
```

모델의 프로퍼티를 JSON 데이터 형식으로 추가합니다. 만약 웹 작업자를 사용하고 있을 경우 오버헤드를 방지하기 위해 `loadJsonDataFromWorker()`를 대신 사용하십시오.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `data`: 키가 expressID이고 값이 프로퍼티인 객체가 데이터입니다. 게다가 각 값은 프로퍼티 `expressID` (항목의 id)와 `type` (항목의 IFC 클래스)을 갖고 있습니다.

#### 예제:

```javascript
await ifcLoader.ifcManager.addModelJSONData(0, jsonData);
```

### loadJsonDataFromWorker

```javascript
async IfcLoader.IfcManager.loadJsonDataFromWorker (
                                        modelID: number,
                                        path: string
                                            ): void;
```

웹 작업자로부터 직접 가져온 JSON 파일로부터 IFC 모델의 데이터를 로드합니다. 만약 웹 작업자를 사용하지 않는다면 대신 `addModelJSONData()`를 이용하십시오.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `path`: JSON 파일의 경로입니다. **웹 작업자 파일에 상대적입니다**.

#### 예제:

```javascript
await ifcLoader.ifcManager.loadJsonDataFromWorker(0, "path/to/data.json");
```

## 게터 (Getters)

### getExpressId

```javascript
IfcLoader.IfcManager.getExpressId (
                        geometry: BufferGeometry,
                        faceIndex: number
                        ): number;
```

면(face) 인덱스로부터 IFC 요소의 Express ID를 가져옵니다.

* 왜 면(face) 인덱스입니까? 왜냐하면 우리가 마우스로 3D 공간에서 객체 하나를 선택할 때 어떤 면(face)의 인덱스를 가져오기 때문입니다. 저희는 일반적으로 그 면이 속한 객체의 ID를 원합니다. 그 다음에는 그 객체를 하이라이트로 표시하거나, 배제시키거나, 그것의 모든 프로퍼티들을 가져옵니다.

#### 인자:

* `geometry`: 당신이 마우스로 클릭한 모델의 [지오메트리](https://threejs.org/docs/#api/en/core/BufferGeometry)입니다.

* `faceIndex`: [raycaster](https://threejs.org/docs/#api/en/core/Raycaster)와 교차하는 면(face)의 인덱스입니다. raycaster가 무엇인지 잘 모르신다면 걱정하지 마십시오; 피킹(picking)에 대한 튜토리얼에서 이것을 자세히 다룰 것입니다.

#### 예제:

```javascript
const intersected = raycaster.intersectObject(mesh)[0];
const index = intersected.faceIndex;
const id = ifcLoader.ifcManager.getExpressId(mesh, index);
```

### getIfcType

```javascript
IfcLoader.IfcManager.getIfcType (
                        modelID: number,
                        id: number,
                        ): string;
```

지정한 요소의 IFC 타입을 가져옵니다. (예. IFCWALL)

* IFC에서 요소들은 항상 연관된 타입을 갖고 있습니다: IfcWall, IfcSlab, IfcWindow, IfcDoor 등.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `id`: 프로퍼티들을 가져올 항목의 Express ID입니다. (만약 3D 뷰에서 객체를 피킹하고 있다면) `getExpressId`로 이것을 가져올 수 있으며, 그 외에도 `getAllItemsOfType` 또는 `getSpatialStructure`를 이용해 모델을 순회하면서 가져올 수도 있습니다.

#### 예제:

```javascript
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const type = manager.getIfcType(model, id);
```

### getAllItemsOfType

```javascript
async IfcLoader.IfcManager.getAllItemsOfType (
                            modelID: number,
                            type: number,
                            verbose: boolean
                            ): number[] | object[];
```

지정한 모델의 지정한 IFC 타입(예. 모든 벽, 모든 바닥, 모든 창 등)의 모든 객체를 리턴합니다. `expressIDs` 배열, 또는 (if `verbose = true`) 발견한 항목들의 프로퍼티들을 포함하는 객체 배열을 리턴할 수 있습니다.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `type`: 당신이 가져오고 싶은 요소들의 IFC 타입입니다. `web-ifc`로부터 직접 이 타입들을 가져올 수 있습니다. (아래 예제를 보십시오)

* `verbose`: 만약 true이면, 발견한 모든 항목들의 프로퍼티들을 가져옵니다. 큰 모델에서는 연산이 느려질 수 있으므로 주의하십시오.

#### 예제:

```javascript
import { IFCWALLSTANDARDCASE as W } from "web-ifc";

const manager = loader.ifcLoader.ifcManager;
const walls = await manager.getAllItemsOfType(0, W, false);
```

### getItemProperties

```javascript
async IfcLoader.IfcManager.getItemProperties (
                            modelID: number,
                            id: number,
                            recursive = false
                            ): object[];
```

주어진 요소의 네이티브 프로퍼티들을 가져옵니다. IFC 스키마에서는 2가지 타입의 프로퍼티가 있습니다: 직접과 간접. 간접 프로퍼티(psets, qsets, type)들을 가져오는 방법은 나중에 설명할 것입니다.

* 프로퍼티와 관련된 모든 메소드는 객체 배열을 리턴합니다. 객체는 키가 프로퍼티의 이름이고 값이 그 프로퍼티의 값입니다.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `id`: 프로퍼티들을 가져올 항목의 Express ID입니다. (만약 3D 뷰에서 객체를 피킹하고 있다면) `getExpressId`로 이것을 가져올 수 있으며, 그 외에도 `getAllItemsOfType` 또는 `getSpatialStructure`를 이용해 모델을 순회하면서 가져올 수도 있습니다.

* `recursive`: 만약 true이면, 참조된 요소들의 모든 프로퍼티들을 재귀적으로 가져옵니다. 큰 모델에서는 연산이 느려질 수 있으므로 주의하십시오.

#### 예제:

```javascript
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const props = await manager.getItemProperties(model, id, false);
```

### getTypeProperties

```javascript
async IfcLoader.IfcManager.getTypeProperties (
                            modelID: number,
                            id: number,
                            recursive = false
                            ): number[] | object[];
```

주어진 요소의 type 프로퍼티들을 가져옵니다.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `id` 프로퍼티들을 가져올 항목의 Express ID입니다. (만약 3D 뷰에서 객체를 피킹하고 있다면) `getExpressId`로 이것을 가져올 수 있으며, 그 외에도 `getAllItemsOfType` 또는 `getSpatialStructure`를 이용해 모델을 순회하면서 가져올 수도 있습니다.

* `recursive`: 만약 true이면, 참조된 모든 요소들의 프로퍼티들을 재귀적으로 가져옵니다. 큰 모델에서는 연산이 느려질 수 있으므로 주의하십시오.

#### 예제:

```javascript
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const props = await manager.getTypeProperties(model, id, false);
```

### getPropertySets

```javascript
async IfcLoader.IfcManager.getPropertySets (
                            modelID: number,
                            id: number,
                            recursive = false
                            ): object[];
```

주어진 요소의 프로퍼티 세트와 수량 세트를 가져옵니다.

* 프로퍼티 세트? 네이티브 및 타입 프로퍼티는 IFC 스키마에 의해 미리 정의된 것입니다: 이것들은 항상 같은 정보를 포함합니다. 반면에 프로퍼티 세트는 임의적이며 사용자가 정의할 수 있습니다.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `id` 프로퍼티들을 가져올 항목의 Express ID입니다. (만약 3D 뷰에서 객체를 피킹하고 있다면) `getExpressId`로 이것을 가져올 수 있으며, 그 외에도 `getAllItemsOfType` 또는 `getSpatialStructure`를 이용해 모델을 순회하면서 가져올 수도 있습니다.

* `recursive`: 만약 true이면, 참조된 모든 요소들의 프로퍼티들을 재귀적으로 가져옵니다. 큰 모델에서는 연산이 느려질 수 있으므로 주의하십시오.

#### 예제:

```javascript
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const props = await manager.getPropertySets(model, id, false);
```

### getMaterialsProperties

```javascript
async IfcLoader.IfcManager.getMaterialsProperties (
                            modelID: number,
                            id: number,
                            recursive = false
                            ): object[];
```

주어진 요소의 재질 정보를 가져옵니다.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `id` 프로퍼티들을 가져올 항목의 Express ID입니다. (만약 3D 뷰에서 객체를 피킹하고 있다면) `getExpressId`로 이것을 가져올 수 있으며, 그 외에도 `getAllItemsOfType` 또는 `getSpatialStructure`를 이용해 모델을 순회하면서 가져올 수도 있습니다.

* `recursive`: 만약 true이면, 참조된 모든 요소들의 프로퍼티들을 재귀적으로 가져옵니다. 큰 모델에서는 연산이 느려질 수 있으므로 주의하십시오.

#### 예제:

```javascript
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const props = await manager.getMaterialsProperties(model, id, false);
```

### getSpatialStructure

```javascript
async IfcLoader.IfcManager.getSpatialStructure (
                        modelID: number
                        ): object;
```

객체의 공간 구조(spatial structure)를 가져옵니다.

* [공간 구조(spatial structure)](https://standards.buildingsmart.org/IFC/DEV/IFC4_2/FINAL/HTML/schema/ifcproductextension/lexical/ifcspatialstructureelement.htm)는 모든 IFC 프로젝트를 구성하는 계층적 구조입니다. (모든 물리적 항목들은 공간 구조의 요소에 참조됩니다)

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

#### 예제:

```javascript
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
const ifcProject = await manager.getSpatialStructure(model);
```

## 서브셋 (Subsets)

### getSubset

```javascript
IfcLoader.IfcManager.getSubset (
                        modelID: number,
                        material?: Material,
                        customID?: string
                        ): object;
```

지정한 [재질](https://threejs.org/docs/#api/en/materials/Material)로 서브셋의 메시(mesh)를 가져옵니다. 만약 주어진 재질이 없으면 이것은 원래 재질을 가진 서브셋을 리턴합니다.

* 기하 서브셋은 모델의 지오메트리를 추출한 것입니다. 예를 들면, 특정 조건을 만족하는 모든 IfcDoors와 IfcWindows로 서브셋을 추출해서 그것들을 하이라이트로 표시하거나 내보낼 수 있습니다.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `material`: (선택적) 서브셋에 할당된 재질입니다. (존재할 경우)

* `customID`: (선택적) 서브셋의 선택적인 커스텀 이름입니다. (존재할 경우)

#### 예제:

```javascript
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
const subset = manager.getSubset(model);
```

### createSubset

```javascript
IfcLoader.IfcManager.createSubset (
                        config: SubsetConfig
                        ): object;
```

새로운 기하 서브셋을 생성합니다.

#### 인자:

* `config`: 다음 옵션들을 갖는 구성 객체입니다:

  * `scene`: 모델이 위치한 장면입니다.

  * `modelID`: 모델의 ID입니다.

  * `ids`: 서브셋과 일치하게 될 모델의 항목들의 Express ID입니다.

  * `removePrevious`: 이 재질을 가진 이 모델의 예전 서브셋을 지울지 여부를 의미합니다.

  * `material`: (선택적) 서브셋에 적용할 재질입니다. 만약 주어진 재질이 없다면 서브셋은 원래 재질을 갖습니다.

  * `customID`: (선택적) 서브셋에 제공할 선택적인 커스텀 이름입니다. 이것은 동일한 재질을 갖는 다수의 서브셋을 만들 수 있게 해줍니다.

#### 예제:

```javascript
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
const config = {
        modelID: model
        scene: scene,
        ids: [id],
        removePrevious: true
}
manager.createSubset(config);
```

### removeSubset

```javascript
IfcLoader.IfcManager.removeSubset (
                        modelID: number,
                        material?: Material,
                        customID?: string,
                        ): object;
```

지정한 기하 서브셋을 제거합니다.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `material`: (선택적) 서브셋에 할당된 재질입니다. (존재할 경우)

* `customID`: (선택적) 서브셋에 제공할 선택적인 커스텀 이름입니다. 이것은 동일한 재질을 갖는 다수의 서브셋을 만들 수 있게 해줍니다.

#### 예제:

```javascript
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
manager.removeSubset(model);
```

### removeFromSubset

```javascript
IfcLoader.IfcManager.removeFromSubset (
                        modelID: number,
                        ids: number[],
                        customID?: string,
                        material?: Material
                        ): void;
```

지정된 기하 서브셋으로부터 지정한 항목들을 제거합니다.

#### 인자:

* `modelID`: IFC 모델의 ID입니다.

* `ids`: 서브셋으로부터 제거할 항목들의 Express ID입니다.

* `customID`: (선택적) 서브셋에 제공할 선택적인 커스텀 이름입니다. 이것은 동일한 재질을 갖는 다수의 서브셋을 만들 수 있게 해줍니다.

* `material`: (선택적) 서브셋에 할당된 재질입니다. (존재할 경우)

#### 예제:

```javascript
import { IFCWALLSTANDARDCASE as W } from "web-ifc";
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
const walls = await manager.getAllItemsOfType(0, W, false);
manager.removeFromSubset(model, walls);
```

## 피킹 (Picking)

So far we have only loaded IFC models into the scene. That's already great, but it would be even better to be able to interact with that model, and that's precisely what we're going to do.

### Import Three.js dependencies

Before you can do things with objects, you need to be able to select them. This can be easily achieved with the [Three.js Raycaster](https://threejs.org/docs/#api/en/core/Raycaster), which can be imported from three's core library. In addition, we will import a [Vector2](https://threejs.org/docs/#api/en/math/Vector2) object to store the mouse position in the scene.

```javascript
import { Raycaster, Vector2 } from "three";
```

* The Raycaster allows you to shoot "beams" that hit objects in the scene and return their information.

### Import three-mesh-bvh (optional)

In addition, we will import [the three-mesh-bvh library](https://github.com/gkjohnson/three-mesh-bvh) to make the selection of objects much more optimal. This can be installed with `npm i three-mesh-bvh`. Don't worry, you don't have to learn how to use that library. Just give us these library objects and IFC.js will take care of the rest.

```javascript
import { acceleratedRaycast, computeBoundsTree, disposeBoundsTree } from "three-mesh-bvh";

// Sets up optimized picking
ifcLoader.ifcManager.setupThreeMeshBVH(computeBoundsTree, disposeBoundsTree, acceleratedRaycast);
```

### Store reference of IFC models

Before doing anything else, it is necessary to save a reference to the IFC models in the scene in order to select them. To do this, we just need to create an array where we store the models we load:

```javascript
//Sets up the IFC loading
const ifcModels = [];
const ifcLoader = new IFCLoader();

async function loadIFC() {
  await ifcLoader.ifcManager.setWasmPath("../../");
  ifcLoader.load("../../IFC/01.ifc", (ifcModel) => {
    ifcModels.push(ifcModel);
    scene.add(ifcModel);
  });
}

loadIFC();
```

### How to do it

Next we will create an instance of the Raycaster and the mouse position vector. To optimise the application, the Raycaster will only retrieve information from the first object it encounters.

```javascript
const raycaster = new Raycaster();
raycaster.firstHitOnly = true;
const mouse = new Vector2();
```

Now we need a function for the Raycaster to cast rays, calculating the position of the mouse on the screen. Note that:

* The threeCanvas object is the HTML `canvas` element where the Three.js scene is being rendered. A reference to it can be retrieved with `getElementByID()`.

* It is necessary to specify which objects the beam collides with. In this case, it will only collide with the loaded IFC models, i.e. if there are more objects in the scene, it will ignore them.

```javascript
function cast(event) {
  // Computes the position of the mouse on the screen
  const bounds = threeCanvas.getBoundingClientRect();

  const x1 = event.clientX - bounds.left;
  const x2 = bounds.right - bounds.left;
  mouse.x = (x1 / x2) * 2 - 1;

  const y1 = event.clientY - bounds.top;
  const y2 = bounds.bottom - bounds.top;
  mouse.y = -(y1 / y2) * 2 + 1;

  // Places it on the camera pointing to the mouse
  raycaster.setFromCamera(mouse, camera);

  // Casts a ray
  return raycaster.intersectObjects(ifcModels);
}
```

We have a function that fires a ray and returns the object it collides with, but we are not doing anything with that object. Let's create a second function that gets the index of the face the ray hit and logs in the console the Express ID of the object it belongs to.

```javascript
function pick(event) {
  const found = cast(event)[0];
  if (found) {
    const index = found.faceIndex;
    const geometry = found.object.geometry;
    const ifc = ifcLoader.ifcManager;
    const id = ifc.getExpressId(geometry, index);
    console.log(id);
  }
}
```

The Raycaster always returns an array of objects, even if *raycaster.firstHitOnly = true;*. In this case, the array will only contain one object that can be extracted with *[0]*.

Finally, all that remains is to associate that function with an event (in this case it's a double click).

```javascript
threeCanvas.ondblclick = pick;
```

If you have done everything right and double click on an item, you will see its Express ID in the console (you can access the console by pressing F12 or by inspecting the page).

### Next steps

Congratulations! You now know how to get the ID of an object by clicking on it. Now we can do many things using that ID.

However, it would be nice if the user could see graphically that the object has been selected. For that, let's go to the next point, where we will learn how to highlight elements.

## Subsets

In almost all BIM applications, elements are highlighted when the user moves the mouse over them or selects them. IFC.js is no exception, and in this tutorial we will see how to achieve this.

[Previously](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/Tutorials/Picking/) we have seen how to obtain the ID of an object on which we cast a ray with the [Raycaster](https://threejs.org/docs/#api/en/core/Raycaster). Now that we have those IDs, it's possible to highlight those elements using **geometric subsets**.

* Geometric subsets?: **Geometric subsets** are any group of items in the model. For example: all doors, all ground floor elements or all elements fulfilling a given condition.

### Import dependencies

We'll need a [material](https://threejs.org/docs/#api/en/materials/Material) to highlight the items. You can choose any material you like; in this example we'll use a [MeshLambertmaterial](https://threejs.org/docs/#api/en/materials/MeshLambertMaterial), which we'll import from Three's core library.

```javascript
import { MeshLambertMaterial } from "three";
```

We'll use the Raycaster, so you'll also need [those dependencies](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/Tutorials/Picking/#import-threejs-dependencies), as well as [three-mesh-bvh](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/Tutorials/Picking/#import-three-mesh-bvh-optional) if we want optimal performance.

## How to do it

### Highlight material

The first thing is to create the **highlight material**. Play with the configuration and make the material look nice! Pro tip: you can use `depthTest=false` so that the object is visible from any viewpoint.

```javascript
// Creates subset material
const preselectMat = new MeshLambertMaterial({
  transparent: true,
  opacity: 0.6,
  color: 0xff88ff,
  depthTest: false,
});
```

Note that geometric subsets are **uniquely identified** by their material.

* If you create a subset with a wall using a material A, and then try to create a subset of another wall with the same material A, the second wall will be added to the subset of the first one.

* If you create a subset with a wall using material A, and then try to create another subset of the same wall using material B, you will have created two independent subsets.

* You can have two separate subsets with the same appearance using two instances of the same material.

### Single subset

We can create a highlight effect when the user hovers with [createSubset](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/api#createsubset).

```javascript
const ifc = ifcLoader.ifcManager;

// Reference to the previous selection
let preselectModel = { id: -1 };

function highlight(event, material, model) {
  const found = cast(event)[0];
  if (found) {
    // Gets model ID
    model.id = found.object.modelID;

    // Gets Express ID
    const index = found.faceIndex;
    const geometry = found.object.geometry;
    const id = ifc.getExpressId(geometry, index);

    // Creates subset
    ifcLoader.ifcManager.createSubset({
      modelID: model.id,
      ids: [id],
      material: material,
      scene: scene,
      removePrevious: true,
    });
  } else {
    // Removes previous highlight
    ifc.removeSubset(model.id, material);
  }
}

window.onmousemove = (event) => highlight(event, preselectMat, preselectModel);
```

There are several interesting things to look out for:

* The implementation of `cast()` was shown [previously](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/Tutorials/Picking/#how-to-do-it).

* The variable `currentModel` is used to store a reference of the selected model; this way, when the user is not hovering an object, we are able to remove the previous subset with [removeSubset](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/api#removesubset).

* The IDs of the items whose subset to create have to be given as an **array** (even if it's a single ID).

### Multiple subsets

Working with **multiple subsets** is as easy as working with a single subset. We just need to create a new material, create a new subset with the same function and associate the creation of that subset to an event.

In this example we are going to bind it to **double click** to simulate the effect of highlighting objects when they are selected.

```javascript
const selectMat = new MeshLambertMaterial({
  transparent: true,
  opacity: 0.6,
  color: 0xff00ff,
  depthTest: false,
});

const selectModel = { id: -1 };
window.ondblclick = (event) => highlight(event, selectMat, selectModel);
```

### Extracting geometry

If you create a geometry subset and do not specify a highlight material, the subset will have the **original materials**.

* This would allow, for example, to create a geometric subset with all the ground floor elements of the BIM model and hide the rest.

In the next example we will apply a transparent material to a copy of loaded IFC model and create a subset with the original materials when the mouse hovers over an item. For this we will use almost the same code as before.

```javascript
ifcLoader.load("../../IFC/01.ifc", (ifcModel) => {
  ifcModel.visible = false;

  const modelCopy = new Mesh(
    ifcModel.geometry,
    new MeshLambertMaterial({
      transparent: true,
      opacity: 0.1,
      color: 0x77aaff,
    })
  );

  scene.add(ifcModel);
  scene.add(modelCopy);
});

// ...

window.onmousemove = (event) => highlight(event, undefined, highlightModel);
```

## Next steps

Congratulations! You should now be able to highlight elements and extract geometry from the BIM model. Good job!

However, don't be so quick to claim victory. We haven't talked about the "I" in BIM yet, and that's even more important than the geometry. That's what the next lesson is for.

## Properties

Although virtually all BIM models have geometry, almost everyone agrees that what is really important is the "I" in BIM, i.e. **Information**. IFC.js can traverse any IFC file from top to bottom at **native speed** and with **almost no code**.

This not only makes it possible to create web applications that **read information from IFC** files directly on the client side, but also to transfer that information into relational or non-relational databases and process it on the backend.

* IFC.js can read IFC files by IDs, by spatial tree and by filtered search.

There are several types of properties in the IFC scheme, each with a specific purpose, and IFC.js can get **all of them**. Some of the most common are:

* Native properties: Specific to each IFC class.

* Type properties: Describe properties of all elements of the same type (e.g. all envelope walls of a particular type).

* Material properties: Describes all the materials that make up the layers of that element.

* Property sets: Arbitrary sets of user-defined properties. There may be multiple sets of properties associated with one or more elements. Each property set contains an arbitrary group of properties related to each other.

* Quantity sets: Sets of properties describing the dimensions of the elements to which they refer. Although it would also be possible to infer element dimensions implicitly from the geometry definition, this explicit description makes it much easier to create applications that measure IFC models.

 But enough theory! Let's get down to work.

## How to do it

### Hello properties

The basic way to extract properties from an IFC is from the ID of an element. In many cases, when the user selects an element, we will want to get its direct and indirect properties. [Previous tutorials](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/Tutorials/Picking/) have shown how to get that ID easily.

Now that we have that ID, how hard it is to get the properties of an element? You only need to add **one line of code** to what we saw in the [picking tutorial](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/Tutorials/Picking/) to be able to see the properties of the selected element when double clicking.

```javascript
// Event that gets executed when an item is picked
async function pick(event) {
  const found = cast(event)[0];
  if (found) {
    const index = found.faceIndex;
    const geometry = found.object.geometry;
    const ifc = ifcLoader.ifcManager;
    const id = ifc.getExpressId(geometry, index);
    const modelID = found.object.modelID;
    const props = await ifc.getItemProperties(modelID, id);
    output.innerHTML = JSON.stringify(props, null, 2);
  }
}
```

#### But what are these properties?

They are **native properties**, that is, the basic properties inherent to each ifc element type. The properties are given as a **JavaScript object**, so they are super easy to traverse.

#### Why do some properties have numbers as values?

These are not numbers, but **express IDs**! This means that you can use `getItemProperties()` again using that ID, and you'll get the properties of that **referenced** element.

* That is how IFC works: each **element** has **properties**, and each **property** can be the reference to other **element**. So you can basically traverse the whole IFC navigating through references.

#### References? But I want all the information directly!

Don't worry, we got you covered! You can use an optional third parameter of `getItemProperties()`, which is a boolean that is false by default. If you set it to true, we will get all referenced elements recursively and give you everything nicely packed in a single JavaScript object.

Nonetheless, we usually recommend avoiding this in order to avoid runtime overheads. Much better is to use `getItemProperties()` only for those IDs you need when you need them.

#### How can I get other types of properties?

The IFC.js API has other similar methods for all other property types: `getTypeProperties()`, `getMaterialProperties()` and `getPropertySets()`. This last method fetches both property sets and quantity sets.

#### Is getItemProperties() the only way to traverse the IFC?

Not at all! We'll see how to traverse the whole spatial structure next.

### Traverse the IFC

You can now browse the IFC information from the ID of an element, and you also know how to get the ID by clicking on objects in the scene. However, we know that **this is not enough**.

* What if you want to get the properties of elements that have no geometric representation (e.g. `IfcSite`)?

* What if you want to traverse the entire spatial structure of the IFC?

Of course, all this is really easy with the IFC.js API.

### Spatial tree

As you may know, all IFCs have a general structure called **Spatial Element Structure** (we'll refer to it as `spatial tree`). It is composed of elements that define the relative position of all products (physical objects) in the project.

* The spatial structure generally consists of IfcProject, IfcSite, IfcBuilding, IfcBuildingStorey and IfcSpace.

You can get the spatial structure of the project simply calling `getSpatialStructure()`, where the only parameter is the `modelID`. This method will return the whole spatial structure of the project as a JavaScript object.

Does this means that you get all the properties of all the products of the project? **Nope**, because that would be computationally expensive. Instead, you get a tree of items with the following information:

```javascript
interface Node {
  expressID: number;
  type: string;
  children: Node[];
}
```

Notice that you only get the **type** (e.g. `IfcWall`) and the **express ID**. If you want to get the properties of an element, you'll have to traverse the tree and call the abovementioned property getter methods over all the IDs.

* If your goal is to display properties to users, it's generally better to only get the properties when the user requests it (e. g. clicks on a specific item in your GUI).

For instance, if you request the spatial structure of a project, you might get something like this:

```
{
    expressID: 100,
    type: "IfcProject",
    children: [{
        expressID: 101,
        type: "IfcSite",
        children: [{
            expressID: 102,
            type: "IfcBuilding",
            children:[
                {
                    expressID: 103,
                    type: "IfcBuildingStorey",
                    children: {...}
                },
                {
                    expressID: 104,
                    type: "IfcBuildingStorey",
                    children: {...}
                }
            ]
        }]
    }]
}
```

### Get items by type

Sometimes you'll want to retrieve **all elements of a certain type** (e.g. all `IfcWall` instances in the project). In these cases it is not useful to select elements by clicking on them or to get the spatial tree of the project.

That's what the `getAllItemsOfType` method is for. Using it is really easy, and you can import the types directly from `web-ifc`. For instance, to get the properties of all the `IfcSlab` instances of the project, you can do the following:

```javascript
import { IFCSLAB } from "web-ifc";

const ifc = ifcLoader.ifcManager;
const modelID = 0;

async function logAllSlabs() {
  const slabsID = await ifc.getAllItemsOfType(modelID, IFCSLAB);

  for (let i = 0; i <= slabsID.length; i++) {
    const slabID = slabsID[i];
    const slabProperties = await ifc.getItemProperties(0, slabID);
    console.log(slabProperties);
  }
}

logAllSlabs();
```

## Next steps

Congratulations! You should now be able to **traverse any IFC** and extract the properties you are looking for.

However, what can we do with these properties? One possible application can be found in the following tutorial, where we will see how to **hide and isolate** elements.

## Hiding

With what we have seen in other tutorials we already know how to select elements in 3D, access their properties and highlight them using **subsets, which are parts of the whole model**.

However, in many BIM applications it is also possible to **hide and isolate elements**. A common use case is to hide all elements that do not comply with a certain filter or show only those objects belonging to a floor of the building.

Of course, this is a piece of cake using IFC.js. In this example we are going to create **filters by category**, so that the user can show or hide items using checkboxes.

* As with the other tutorials, you can find the full example [here](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-three/hiding).

## How to do it

### Get subsets of categories

Visibility in IFC.js is based on **subset operations**. This allows complex visualisations to be created with minimal memory usage. The first thing we are going to do is to define which **IFC categories** we are going to allow the user to show or hide.

To save memory, **categories in IFC.js are defined as numeric constants**. So let's create an object that maps the name of those constants to their numeric value, and a function to retrieve them:

```javascript
import { IFCWALLSTANDARDCASE, IFCSLAB, IFCDOOR, IFCWINDOW, IFCFURNISHINGELEMENT, IFCMEMBER, IFCPLATE } from "web-ifc";

// List of categories names
const categories = {
  IFCWALLSTANDARDCASE,
  IFCSLAB,
  IFCFURNISHINGELEMENT,
  IFCDOOR,
  IFCWINDOW,
  IFCPLATE,
  IFCMEMBER,
};

// Gets the name of a category
function getName(category) {
  const names = Object.keys(categories);
  return names.find((name) => categories[name] === category);
}
```

Now let's create a couple of functions to **get all the IDs** of the elements belonging to a category and **create a subset** with those IDs.

* Remember that many IFC.js functions are asynchronous, so we're going to use async and await.

You can also use `removeFromSubset()` to remove a single item from a subset (e.g. hide a single item). If you combine that with `createSubset()` with `removePrevious = false`, you'll have full control of what is added to which subset and its visibility.

```javascript
// Gets the IDs of all the items of a specific category
async function getAll(category) {
  const manager = ifcLoader.ifcManager;
  return manager.getAllItemsOfType(0, category, false);
}

// Creates a new subset containing all elements of a category
async function newSubsetOfType(category) {
  const ids = await getAll(category);
  return ifcLoader.ifcManager.createSubset({
    modelID: 0,
    scene,
    ids,
    removePrevious: true,
    customID: category.toString(),
  });
}
```

### Set up GUI

We will now create a simple GUI to allow the user to control which categories are visible or invisible. We are going to **create a checkbox for each category** of the BIM model we are working with.

This can easily be done with a little **HTML** and **CSS**:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" href="../../../favicon.ico" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="styles.css" />
    <title>IFC.js</title>
  </head>
  <body>
    <canvas id="three-canvas"></canvas>

    <div class="checkboxes">
      <div>
        <input checked="true" id="IFCWALLSTANDARDCASE" type="checkbox" />
        Walls
      </div>
      <div>
        <input checked="true" id="IFCSLAB" type="checkbox" />
        Slabs
      </div>
      <div>
        <input checked="true" id="IFCWINDOW" type="checkbox" />
        Windows
      </div>
      <div>
        <input checked="true" id="IFCFURNISHINGELEMENT" type="checkbox" />
        Furniture
      </div>
      <div>
        <input checked="true" id="IFCDOOR" type="checkbox" />
        Doors
      </div>
      <div>
        <input checked="true" id="IFCMEMBER" type="checkbox" />
        Curtain wall structure
      </div>
      <div>
        <input checked="true" id="IFCPLATE" type="checkbox" />
        Curtain wall plates
      </div>
    </div>

    <script src="bundle.js"></script>
  </body>
</html>
```

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  overflow: hidden;
}

#three-canvas {
  position: fixed;
  top: 0;
  left: 0;
  outline: none;
}

#file-input {
  z-index: 1;
  position: absolute;
}

.checkboxes {
  position: absolute;
  left: 1rem;
  top: 1rem;
}
```

### Bind GUI with visibility

Now it only remains to **link the click event of each checkbox with the visibility of the corresponding category**, so that when the checkbox is activated the category becomes visible and when it is deactivated it disappears.

Here it is worth noting that to make the code more concise we have given **each checkbox an ID with the same name as the category it links to**.

```javascript
// Stores the created subsets
const subsets = {};

async function setupAllCategories() {
  const allCategories = Object.values(categories);
  for (let i = 0; i < allCategories.length; i++) {
    const category = allCategories[i];
    await setupCategory(category);
  }
}

// Creates a new subset and configures the checkbox
async function setupCategory(category) {
  subsets[category] = await newSubsetOfType(category);
  setupCheckBox(category);
}

// Sets up the checkbox event to hide / show elements
function setupCheckBox(category) {
  const name = getName(category);
  const checkBox = document.getElementById(name);
  checkBox.addEventListener("change", (event) => {
    const checked = event.target.checked;
    const subset = subsets[category];
    if (checked) scene.add(subset);
    else subset.removeFromParent();
  });
}
```

And here is the result:

## Next steps

Congratulations! Now you know how to control the visibility of elements using any filter.

* This would be the same if we want to filter with other properties (e.g. the floor they belong to using the spatial structure tree, seen in the properties section). Just make sure you get the IDs of the elements you want to filter.

However, `web-ifc-three` has even more functionality. For example, what if we want to **open and close the viewer**? Let's take a look at it next.

## Memory

On many occasions we will want to create applications that are able to **open and close BIM viewers**. Although this may seem obvious, there is a problem: **memory management**.

Now many will be scratching their heads, since memory management is not a common issue in web applications. JavaScript and other modern languages have **automatic memory management / garbage collector**, so the programmer doesn't have to worry about freeing up objects and arrays.

However, when working with Three.js, data going to the graphics card (e.g. buffers) is **not affected by this automatic memory management**.

That means that if we close a viewer made with Three.js (with or without IFC.js), we will create a **memory leak**. That is to say, we are blocking a part of the user's RAM memory. If the leak becomes too big, the application will become slower and slower and may **crash**.

* You can find more information about this topic here.

This becomes especially critical if we are creating a **SPA (Single Page Application)**, for example, using frameworks and libraries such as **React** or **Angular**. In these cases the web application is never reloaded, and the memory leak accumulates.

Fortunately, IFC.js has taken this into account and allows you to **release the used memory very easily**. Let's see how.

* You can find the full example of this tutorial [here](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-three/memory).

## How to do it

### Monitoring the memory

The first question you probably have if you haven't worked much with Three.js optimized scenes is how to see **how much memory your application consumes**. Otherwise, it is impossible to detect memory leaks.

There are several ways to do this. The first is to use the **developer tools** of the browser you are using. For example, in Google Chrome there is a section called "Memory" where you can take snapshots and see how much memory the current tab is consuming.

However, a more convenient way is to use the library [stats.js](https://github.com/mrdoob/stats.js/). This library allows to **monitor the performance and memory** of a Three.js application. It can be installed with `npm i stats.js` and can be used as follows:

```javascript
// Stats
const stats = new Stats();
stats.showPanel(2);
document.body.append(stats.dom);

// Animation loop
const animate = () => {
  stats.begin();

  // Update other stuff
  stats.end();
  requestAnimationFrame(animate);
};

animate();
```

This will bring up the **scene statistics during execution**. By clicking on them we can toggle between performance and memory usage of the app.

### Dispose memory

Now let's create a function that removes all the memory consumed by IFC.js. There are 2 things to keep in mind:

* If we have specified the **path to the WASM files** previously, we will have to do it again in the new instance of web-ifc-three.

* This one is important: if we have stored a reference to the loaded IFC models in an array, an object or a class, **we have to delete them manually**. Otherwise, the memory will not be freed.

```javascript
async function releaseMemory() {
  // This releases all IFCLoader memory
  await ifcLoader.ifcManager.dispose();
  ifcLoader = null;
  ifcLoader = new IFCLoader();

  // If the wasm path was set before, we need to reset it
  await ifcLoader.ifcManager.setWasmPath("../../../");

  // If IFC models are an array or object,
  // you must release them there as well
  // Otherwise, they won't be garbage collected
  models.length = 0;
}
```

### Set up simple GUI

Finally, we are going to create an HTML button and link it to the function we created earlier.

```html
<input type="button" id="memory-button" value="Release memory" />
```

```javascript
// Sets up memory disposal
const button = document.getElementById("memory-button");
button.addEventListener(`click`, () => releaseMemory());
```

This is how the application looks like:

Try loading a model and releasing the memory: you'll see it go back to normal. Beware that **it can take some seconds**, as the browser garbage collector takes some time. Alternatively, you can manually apply the garbage collector using the browser's developer tools.

### SPA

It is very common to create **SPA** or **Single Page Applications** because they are more efficient and require less communication with the backend. Examples of tools to make these applications are **React**, **Angular**, **Vue**, etc.

In many cases **these tools manage the lifecycle of the application components automatically**. For example, when the user closes the 3d view, the HTML element containing the view is automatically destroyed.

To avoid memory leaks, it will be necessary to **free the application memory as seen in this tutorial each time the component containing the 3D view is destroyed**. In many cases there are hooks or similar mechanisms to execute this logic automatically each time the component is destroyed.

## Next steps

Congratulations! You now know how to manage the memory of the BIM applications you create with IFC.js, so your applications will be 100% free of memory leaks.

Next we are going to look at some advanced model loading tools, such as multithreading and load process event.

## Multithreading

Everything seen so far is very cool, but we have a problem: when we load a very large model **the application freezes for some seconds**. This problem also happens when we want to extract many properties from the model. Is there any way to avoid this?

Of course, IFC.js has foreseen this situation and has implemented **multithreading**. This means that heavy operations will be carried out in a parallel process that will not block the application, which will be updated asynchronously when the process concludes.

This sounds complicated, and it is. But don't worry: we've got it all set up so you can have this in your BIM applications in a couple of lines of code.

* You can find the full example of this tutorial [here](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-three/multithreading).

## How to do it

### Set up the webworker

In order to enable multithreading, the **webworker** must be configured. But what is a webworker? The webworker is the mechanism that web browsers have to be able to work with multithreading. But don't worry if you haven't heard of them before, **you don't need them to use multithreading in IFC.js**.

If you work with `npm`, `yarn` or another package manager in your project there should be a folder called `node_modules`, with all the folders of the libraries your project is using. In `node_modules/web-ifc-three` you will find the two files needed to use webworkers: `IFCWorker.js` and `IFCWorker.js.map`.

* You have to copy these two files to a directory in your project that will be served with the final application. This varies depending on the technology you are using (vanilla JS, React, Angular, etc). You can use the same directory you are using for the wasm files.

Then you have to specify where this file is located, in the same way as with the wasm file. This can be done like this:

```javascript
async function setUpMultiThreading() {
  const manager = ifcLoader.ifcManager;
  // These paths depend on how you structure your project
  await manager.useWebWorkers(true, "IFCWorker.js");
  await manager.setWasmPath("../../../");
}

setUpMultiThreading();
```

And, voi lá! Believe it or not, you have already enabled multithreading in your project. If you now try to load a file in your application or try to get many properties at once, you will see that **the application does not freeze**.

* Note that if you activate the webworker, the path to the wasm files must be relative to the webworker.

Keep in mind that **the version of the webworker has to match the version of the library** you are using. This means that if you update the version of `web-ifc-three` in the future, you'll need to copy these files again. You can automate this using a command-line library to copy files like `cpy`.

### Loading progress

Using multithreading in your BIM application has numerous advantages. The most immediate is that we can now **show the user the loading progress of a model**. First we'll add a simple HTML message to show the progress:

```html
<div id="text-container">
<p>Progress:</p>
<p id="progress-text">0</p>
<p>%</p>
</div>
```

Next we are going to **link this HTML element to the model load event**. This can be easily done with the `setOnProgress()` method. Let's also apply some basic math to **convert progress into a percentage**.

```javascript
function setupProgressNotification() {
  const text = document.getElementById("progress-text");
  ifcLoader.ifcManager.setOnProgress((event) => {
    const percent = (event.loaded / event.total) * 100;
    const result = Math.trunc(percent);
    text.innerText = result.toString();
  });
}

setupProgressNotification();
```

If you have done everything correctly, we should be able to see the following viewer. If you try to load an IFC model, not only you will see that **the loading process does not block the 3D view**, but the **html text shows the loading progress in real time**.

## Next steps

Congratulations! You can now **create multithreaded BIM applications** that never freeze.

You are now familiar with some advanced tools of IFC.js, but there's much more to learn. In later tutorials we will see how to not only read, but also **edit and create IFC files**.

## Mapbox

[Mapbox GL JS](https://docs.mapbox.com/mapbox-gl-js/) is a library that can be paired with IFC.js to provide **worldly context** for your models. Building on top of our knowledge from previous tutorials, we're going to find out how to **view our models inside a custom map**.

* We all have different learning styles. Check out the [Github repo](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-three/mapbox) for the full working example. This tutorial was modeled after [this Mapbox example](https://docs.mapbox.com/mapbox-gl-js/example/add-3d-model/).

## How to do it

### Groundwork

We'll get you up and running with a simple map instance, but do check out the Mapbox GL JS [docs](https://docs.mapbox.com/mapbox-gl-js/) for more **in-depth guides** and sweet **examples**. Let's first load the Mapbox dependencies — in this guide we'll just add them with HTML tags.

```html
<script src='https://api.mapbox.com/mapbox-gl-js/v2.8.2/mapbox-gl.js'></script>
<link href='https://api.mapbox.com/mapbox-gl-js/v2.8.2/mapbox-gl.css' rel='stylesheet' />
```

Then add a simple `div` to hold our map:

```html
<div id="map"></div>
```

Some styling

```css
#map {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
```

And finally some imports from `web-ifc-three` and `three` that we'll use later on.

```javascript
import {
  Matrix4, Vector3,
  DirectionalLight, AmbientLight,
  PerspectiveCamera, Scene, WebGLRenderer,
} from "three";
import { IFCLoader } from "web-ifc-three/IFCLoader";
```

### Init map

With our structure in place, let's initialize our map.

```javascript
mapboxgl.accessToken = 'YOUR_API_KEY_HERE';
const map = new mapboxgl.Map({
  container: 'map',
  style: 'mapbox://styles/mapbox/light-v10',
  zoom: 20.5,
  center: [13.4453, 52.4910],
  pitch: 75,
  bearing: -80,
  antialias: true
});
```

* You must make a free [Mapbox account](https://account.mapbox.com/auth/signup/) to get your own API key.

### Prepping our model

In order for Mapbox to display our model correctly, we need to define our **position, rotation and scale** in map terms.

```javascript
const modelOrigin = [13.4453, 52.4910];
const modelAltitude = 0;
const modelRotate = [Math.PI / 2, .72, 0];

// translate to map coordinates
const modelAsMercatorCoordinate = 
mapboxgl.MercatorCoordinate.fromLngLat(modelOrigin, modelAltitude);

const modelTransform = {
    translateX: modelAsMercatorCoordinate.x,
    translateY: modelAsMercatorCoordinate.y,
    translateZ: modelAsMercatorCoordinate.z,
    rotateX: modelRotate[0],
    rotateY: modelRotate[1],
    rotateZ: modelRotate[2],
    scale: modelAsMercatorCoordinate.meterInMercatorCoordinateUnits()
};
```

Depending on your model, you may have to tweak the `modelOrigin`, `modelAltitude` and `modelRotate` to get things fitting right.

* If your coordinates aren't returning the place you expected, **try swapping** them! Mapbox uses **longitude**, **latitude** coordinates to match geoJSON.

### Setting the scene

Now we'll start to configure our **Three.js scene** for our **custom Mapbox layer**. First some larger scope **definitions**:

```javascript
const scene = new Scene();
const camera = new PerspectiveCamera();
const renderer = new WebGLRenderer({
  // here we inject our Three.js scene into Mapbox
  canvas: map.getCanvas(),
  antialias: true
});
renderer.autoClear = false;
```

Then in `customLayer` we'll include an `onAdd` function to **load our IFC model** and some **lighting** to the scene, as well as a `render` function to apply our **position, rotation and scale** changes.

```javascript
const customLayer = {

    id: '3d-model',
    type: 'custom',
    renderingMode: '3d',

    onAdd: function () {

        //load model
        const ifcLoader = new IFCLoader();
        ifcLoader.ifcManager.setWasmPath( '../../../' );
        ifcLoader.load( '../../../IFC/01.ifc', function ( model ) {
            scene.add( model );
        });

        //add lighting
        const directionalLight = new DirectionalLight(0x404040);
        const directionalLight2 = new DirectionalLight(0x404040);
        const ambientLight = new AmbientLight( 0x404040, 3 ); 
        directionalLight.position.set(0, -70, 100).normalize();
        directionalLight2.position.set(0, 70, 100).normalize();

        scene.add(directionalLight, directionalLight2, ambientLight);
    },

    render: function (gl, matrix) {

        //apply model transformations
        const rotationX = new Matrix4().makeRotationAxis(new Vector3(1, 0, 0), modelTransform.rotateX);
        const rotationY = new Matrix4().makeRotationAxis(new Vector3(0, 1, 0), modelTransform.rotateY);
        const rotationZ = new Matrix4().makeRotationAxis(new Vector3(0, 0, 1), modelTransform.rotateZ);
        
        const m = new Matrix4().fromArray(matrix);
        const l = new Matrix4()
        .makeTranslation(modelTransform.translateX, modelTransform.translateY, modelTransform.translateZ)
        .scale(new Vector3(modelTransform.scale, -modelTransform.scale, modelTransform.scale))
        .multiply(rotationX)
        .multiply(rotationY)
        .multiply(rotationZ);
        
        camera.projectionMatrix = m.multiply(l);
        renderer.resetState();
        renderer.render(scene, camera);
        map.triggerRepaint();
    }
};
```

The last thing to do is simply add our `customLayer` when our map style is loaded.

```javascript
map.on('style.load', () => {
    map.addLayer(customLayer, 'waterway-label');
});
```

### The result

[Github repo](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-three/mapbox)

## Next steps

Yoohoo! You should now be able to **load your model into Mapbox** and place it anywhere in the world you'd like.

---

# web-ifc-viewer

## Contribute

Have you already decided to contribute to the `web-ifc-viewer` library? Congratulations on that wise decision, let's start...

If you are new, [Check it out!](https://ifcjs.github.io/info/docs/Introduction) Here, you can learn about the possibilities and features of IFC.

## Documentation

The contribution must be made in the IFCjs/info repository https://github.com/IFCjs/info. We use docusaurus for documentation. Don't worry, you don't need to know Docusaurus to do this.

## Setup

To get started with a viewer, you can get one from the official IFC repository on Github, https://github.com/IFCjs/web-ifc-viewer. In it we will check the methods.

* To run the application locally we will need a local server. If you're using **VS Code** as your IDE, one option is to install the Live Server extension, which allows us to open an instance of Google Chrome, run our web application, and see the changes we make to the code in real time.

## Tools

With these tools you can make your contribution more dynamic and illustrative.

### Alert

Adds a blue alert window containing an animated icon(💡) Color:(#1a73e8).

#### Example:

```javascript
import { IfcAlert } from "../../../src/components/Alert/Alert";

<IfcAlert>Write here your text to display inside `IfcAlert`</IfcAlert>;
```

### Card

Add a gray card, it can contain icon. Color:(#f3f4f6).

#### Example:

```javascript
import { IfcCard } from "../../../src/components/Card/InfoCard";

<IfcCard icon="🏆" title="TITLE">
  Write here your text to display inside `IfcCard`
</IfcCard>;
```

### Scene

Add a `Scene` with a link.

#### Example:

```javascript
import { Scene } from "../../../src/components/Scene/Scene";

<Scene link={"https://ifcjs.github.io/hello-world/examples/web-ifc-three/helloworld/"} />;
```

### Tab

Add selectable tab.

#### Example:

```javascript
import { Tab } from "../../../src/components/Tab/Tab";

<IfcTab
  items={[
    {
      icon: "🤖",
      content: (
        <p>
          <b>Font bold</b>
          <a href="LINK/">NAMELINK</a>
        </p>
      ),
    },
    {
      icon: "🦅",
      content: (
        <p>
          <i>Font italics </i>
        </p>
      ),
    },
  ]}
/>;
```

### Titles

We can order the titles and establish a development tree thanks to their sizes.

### Congratulations

Below is an example of how to expose a function and its features. You can also use this same document to develop your own contribution to IFC.

## Introduction

As discussed in the [Getting Started](https://ifcjs.github.io/info/docs/Guide/Getting%20started.mdx) guide - web-ifc-three viewer is a 3D BIM viewer with many tools and functionalities already implemented (section drawings, dimensions, etc.), allowing you to create BIM tools with very little effort.\ It is suggested to use this when you want to create a BIM viewer and you don't want to spend time implementing all the model navigation tools you would like to have.

## Setting up the project

The [Hello World](https://ifcjs.github.io/info/docs/Hello%20world.mdx) guide talks about the basic set-up of a ifc.js project. But with web-ifc-viewer the set-up becomes even more simpler because most of the set-up is already done for you.

The first thing to do is to create an empty folder and [start a new npm project](https://docs.npmjs.com/cli/v8/commands/npm-init) with the command `npm init`. This will generate a package.json file containing some data such as the project name, version, commands and dependencies

### Installing libraries

The next step is to install the dependencies necessary for this project. Below are the commands that install the respective dependencies:

```bash
//Install web-ifc-viewer
npm i web-ifc-viewer

// Install a bundler: we will use rollup.js for this guide
npm i rollup --save-dev
npm i @rollup/plugin-node-resolve --save-dev
```

* three.js? Note that installing web-ifc-three also installs the three.js library which allows you to customize the viewer as required in the next steps

### HTML, CSS, Bundling & WASM files

You can follow the steps in the [Hello World](https://ifcjs.github.io/info/docs/Hello%20world.mdx) guide to create the `index.html`, `styles.css`, `rollup.config.js` files and also copy the necessary `.wasm` files from `node_modules\web-ifc` (or `node_modules\three\examples\jsm\loaders\ifc` folder.

* minor change in index.html: Note that there is one minor change in index.html file you need to make - compared to the "Hello World" guide. You don't need to create a `canvas` element manually as it will b created by web-ifc-viewer for you. But you do need to add the container element in which the viewer is supposed to be placed in.

Replace `<canvas id="three-canvas"></canvas>` from you `index.html` file with `<div id="viewer-container"></div>`

* What else can I do with IFC.js? To run the application locally we will need a local server. If you are using VS Code as IDE, one option is to install the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer), which allows us to open an instance of Google Chrome, run our web application and see the changes we make to the code in real-time.

## Setting up 3D-Scene (web-ifc-viewer)

Once you have the `index.html`, `styles.css` & the `.wasm` files in place, you can then move on to adding the javascript(`index.js`) which will load the viewer. This file can be located anywhere and have any name, but you must reflect this in the `rollup.config.js`.

Below code is where we are setting up a basic threejs scene using `IfcViewerAPI()` method of `web-ifc-viewer`. Note that this code is just the viewer - In the next step we will add the functionality to load models into this viewer.

```javascript
import { Color } from "three";
import { IfcViewerAPI } from "web-ifc-viewer";

const container = document.getElementById("viewer-container");
const viewer = new IfcViewerAPI({
  container,
  backgroundColor: new Color(0xffffff),
});
viewer.axes.setAxes();
viewer.grid.setGrid();

const input = document.getElementById("file-input");

window.ondblclick = () => viewer.IFC.selector.pickIfcItem(true);
window.onmousemove = () => viewer.IFC.selector.prePickIfcItem();
viewer.clipper.active = true;

window.onkeydown = (event) => {
  if (event.code === "KeyP") {
    viewer.clipper.createPlane();
  } else if (event.code === "KeyO") {
    viewer.clipper.deletePlane();
  }
};
```

## Loading IFC files

### Loading user's models

Finally, we will use IFC.js to load IFC files by allowing the user to choose a local file and using the `IfcViewerAPI()` we instantiated above to load the model.

```javascript
input.addEventListener(
  "change",

  async (changed) => {
    const file = changed.target.files[0];
    const ifcURL = URL.createObjectURL(file);
    viewer.IFC.loadIfcUrl(ifcURL);
  },

  false
);
```

### Loading our models

In order to load a ifc file from a server, you need to use the `loadIfcUrl()` to convert the model path url into something that the web-ifc-viewer can read. Below is a function `loadIfc(url)` that is used to do that.

```javascript
async function loadIfc(url) {
  const model = await viewer.IFC.loadIfcUrl(url);
  viewer.shadowDropper.renderShadow(model.modelID);
}

// load model from the below path in your repository
loadIfc("models/01.ifc");
```

If you have done everything correctly, you should be able to see something similar to [this](https://ifcjs.github.io/hello-world/examples/web-ifc-viewer/hello-world/) in your local server.

## Conclusion

Congratulations! You have just created your first IFC viewer. Go to the next pages of the docs to find out what else can you do with IFC Viewer.

* What else can I do with IFC.js? This is just the beginning. You can take a look at [web-ifc-viewer examples](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-viewer), which includes tools for floor plans, changing geometry visibility, floor plans and much more. You can try it [here](https://ifcjs.github.io/web-ifc-viewer/example/index).

In the next set of articles, we will talk about how to enable additional in-build features in web-ifc-viewer.

## Json Property

As you might know, IFC is a data schema and what we call as a '.ifc' file is a STEP-File that is widely used to exchange data for 3D objects. This STEP-File is in text format and is not designed as a database. Wanting to be fast reading a single text file is like wishing to go as fast as a car, but with a cycle.

While IFC.js is super efficient and it works well for medium IFC models, its not the most efficient especially for bigger models and thus you can't except high performance when making concatenated queries. There are ways to gain efficiency in this kind of queries: the easiest one is to generate a JSON with the properties and query that JSON instead.

Here, we will learn how to deal with this situation, so nothing can stop us, no matter how big the IFC model is!

* Check out this wiki link for details on [IFC file format](https://en.wikipedia.org/wiki/Industry_Foundation_Classes#File_Formats)

Thankfully IFC.js allows you to pre-process the properties and geometry of an IFC model and convert it to something much more efficient. Specifically, convert the properties to JSON and the geometry to GLB files. After this preprocessing, even big models will run like a charm on any browser. This will make loading and working with files faster and more efficient.

Enough theory. Lets see how to convert the properties to JSON.

## How to do it

### Loading the file

Let's start out by loading our **IFC file**. This is done through `loadIfcUrl()` method

```javascript
async function init() {
    await viewer.IFC.setWasmPath(wasmPath); 
    const model = await viewer.IFC.loadIfcUrl(url);
    }
```

### Serializing all properties

Next, we take all the properties of the model and serialize them, that means, we will create a JSON file with all the properties. The idea beind this is to take properties from JSON instead of IFC directly. This way, you will be able to get the properties an order of magnitude much faster and is super efficient.

IFC.js makes it super easy with the built in `serializeAllProperties()` method. This method serializes all the properties of an IFC (exluding the geometry) into an array of Blobs.

```javascript
const properties =  await viewer.IFC.properties.serializeAllProperties(model);
```

* Working with JSON is also more convenient as you can put the JSON file into a database like MongoDB.

* As an alternative, you can also generate JSON properties along with geometry by using the method `viewer.GLTF.exportIfcFileAsGltf()` with option `getProperties: true`

### Downloading JSON file

Now that we have serialized all the properties and generated the JSON file, let's go ahead and download this file. We can then use this downloaded JSON file for our super efficient IFC model.

In the code below we are creating a link that downloads the JSON file when we open the page

```javascript
const file = new File(properties, 'properties');
const link = document.createElement('a'); 
document.body.appendChild(link);
link.href = URL.createObjectURL(file);
link.download = 'properties.json';
link.click();
link.remove();
```

### Github code

Check out the generated JSON file and the implementation of the code in the Github [page](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-viewer/JSON-property-example)

### Result

Congratulations! You now have all the properties from the IFC file in a much efficient JSON format. If you open this file with Visual Studio Code and format it, you will see that this is all the data from the IFC, but in JSON format.

* Go ahead and save this in a front-end database and make your application way way faster.

## Picking

Now that you're able to load models into your scene, we can jump into functionalities that make `web-ifc-viewer` really shine. Here we'll learn to make our models a little more **interactive**, using **picking functions** from the IFC.js API.

* Dig into the code and check out all the details about the [selection](https://github.com/IFCjs/web-ifc-viewer/tree/master/viewer/src/components/ifc/selection) component methods on Github.

## How to do it

### Easy pickings

Let's start out by using our mouse to highlight different parts of our model when **hovered**. Thankfully IFC.js makes it easy with the built in method `prePickIfcItem()`.

```javascript
window.onmousemove = () => viewer.IFC.selector.prePickIfcItem()
```

* Under the hood web-ifc-viewer borrows the [Raycaster](https://threejs.org/docs/index.html?q=raycaster#api/en/core/Raycaster) from Three.js. And since IFC.js created the official [IFCLoader](https://threejs.org/examples/webgl_loader_ifc.html) for Three.js, it's a beautiful marriage!

### Preserve the pick

Now, let's use `pickIfcItem()` to preserve our selection and then **center our model** in the camera's view.

```javascript
window.onclick = () => viewer.IFC.selector.pickIfcItem(true)
```

* If you don't want to center the model, just leave the first argument of *pickIfcItem()* empty, which defaults to *false*.

If we go a step further and **destructure** the selection, we return information very useful in other IFC.js methods, such as `getProperties()`.

```javascript
window.onclick = async () => {
  const {modelID, id} = await viewer.IFC.selector.pickIfcItem(true);
    const props = await viewer.IFC.getProperties(modelID, id, true, false);
    console.log(props);
}
```

### Highlighting

What if we wanted to **isolate** a certain part of our model and hide the rest? This is where `highlightIfcItem()` comes in handy. We'll just attach it to the `ondblclick` event for now.

```javascript
window.ondblclick = viewer.IFC.selector.highlightIfcItem(true)
```

### Clear it up

Maybe we went a bit wild with our clicking and selecting. So let's call `unpickIfcItems()` and `unHighlightIfcItems()` to clear our doings with our `C` key.

```javascript
window.onkeydown = (event) => {
    if(event.code === 'KeyC') {
        viewer.IFC.selector.unpickIfcItems();
        viewer.IFC.selector.unHighlightIfcItems();
    }
}
```

### Getting specific

In some situations, we may want to use our **Express ID's** to interact with the model in a different way. In this tutorial we'll add a simple button to let the user highlight a part of the model that isn't so easily visible.

Let's quickly **add a button** with some styling.

```html
<button id="express_22492">Front Door</button>
<!-- style to your preference  -->
```

And finally specify our **Express ID** in the event handler with the `pickIfcItemsByID()` method,

```javascript
document.getElementById('express_22492')
.addEventListener('click', () => {
    viewer.IFC.selector.pickIfcItemsByID(0, [22492], true);
})
```

## The result

Here is an example of everything we've learned today:

[Github repo](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-viewer/picking/)

## Next steps

Congrats! You now know how to **pick** and **highlight** your model in a handful of different ways. Now it's up to you to use the tools creatively in your own project!

## Socket.IO

With unlimited power of IFC.js at your fingertips you can now easily view and perform operations on IFC files easily. What about **networking**? In this tutorial we will learn how to share camera position over **Socket.IO** and view it in other user's browser.

* Dig into the code and check out all the details about the [Socket.IO Integration](https://github.com/aka-blackboots/hello-world/tree/main/examples/web-ifc-viewer/socket-io) on Github.

## Import dependencies

### Express

```bash
npm install express
```

Express provides us with tooling for HTTP server, it is framework based upon Node.

### Socket.IO

```bash
npm install socket.io
```

Socket.IO provides bi-directional communication between a server and client.

## How to do it

### Folder Structure

For this tutorial, our folder strucutre will be a little different, but if you've been following other tutorials. This will be easy!

#### index.js

Create a `index.js` file, this file will hold the code for **Server Management**. We will create a express app and using that app we will create a server using **Socket.IO**

```javascript
const express = require('express');

// Creating a express app
const app = express();
const http = require('http');
const server = http.createServer(app);

const { Server } = require("socket.io");
// Creating Socket Server
const io = new Server(server);


app.get('/', (req, res) => {
    res.sendFile(__dirname + '/index.html');
});
```

#### Static Folder

We will use this folder to store all the files that will be necessary and will be served to user when they open the browser. Let's get started by creating a `static` folder inside your directory. Add `wasm` files and `ifc` files into this folder.

```javascript
// Adding Static Folder path, which will be used to store required files
app.use("/static", express.static('./static/'));
```

#### Socket

We can consider Socket as data forwarder, whenever there is connection made to **Server** we will send out the camera position to other clients connected on network.

```javascript
// Connection Event which is triggered when someone enters their initials and is registered on network
io.on('connection', (socket) => {
    socket.on('username', (initials) => {
        console.log('Connected User'+initials);
    });

    // When Client Camera is moved we will Emit this data to other Clients
    socket.on('camera_move', (data) => {
        data.id = socket.id;
        io.emit('camera_move', data);
    });

    socket.on('disconnect', () => {
        console.log('User Disconnected');
    });
})
```

### Getting User Initials/Details

We will get User Initials from a basic **form** which will be created inside `index.html`

```html
<div id="socket-connection-form">
    <label for="initials-name">Enter Your Initials</label><br>
    <input maxlength="2" type="text" id="initials-name" name="initials-name"><br>
    <button id="socket-Connect-Button" onclick="connectToSocket()">Connect</button>
</div>

// Socket.IO creates a local client folder
<script src="/socket.io/socket.io.js"></script>

// Bundle File will be fetched from static folder    
<script src="static/bundle.js"></script>
```

When user clicks on **Connect** button a call to `connectToSocket` will be made which will create the connection.

### Getting Camera Position and Sending to Server

Importing and Variables

```javascript
import {
    CSS2DObject
} from 'three/examples/jsm/renderers/CSS2DRenderer';

let socket;
// To Store your Position
let clients = {}; 
// To Store the Positions of other user's Camera Location
let pointers = {};
```

Once the button is clicked we need to Pass the Initials user has entered with **Camera** position, **Initials** will help to visualise the User's camera position as label created using [CSS2DRenderer](https://threejs.org/docs/#examples/en/renderers/CSS2DRenderer)

This code will be a little lengthy but trust us, it is easy!

```javascript
function connectToSocket() {
    const initials = document.getElementById("initials-name").value;
    console.log(initials)

    if (initials) {
        const connectButton = document.getElementById("socket-Connect-Button");
        connectButton.innerHTML = "Connected!";
        connectButton.disabled = true;

        socket = io();
        console.log(initials + ":Connecting to socket");
        socket.emit('username', initials);

        socket.on('camera_move, function (data) {
            if (!clients.hasOwnProperty(data.id)) {
                // Creating a New Label when there are no previous Labels available
                const labelDiv = document.createElement('div');
                labelDiv.className = 'label';
                labelDiv.textContent = data.initials;
                labelDiv.style.marginTop = '-1em';

                // Passing the Label div to CSS2DObject()
                pointers[data.id] = new CSS2DObject(labelDiv);
                pointers[data.id].position.set(data.x, data.y, data.z);
                viewer.context.scene.add(pointers[data.id]);
                pointers[data.id].layers.set(0);
            }

            // Updating the Label position according to new Data
            pointers[data.id].position.set(data.x, data.y, data.z);

            clients[data.id] = data;
        });

        // Updating Camera Position every time it is updated and sending it using emit()
        viewer.context.ifcCamera.cameraControls.addEventListener('update', e => {
            const cameraPos = {
                "initials": initials,
                "id": "",
                "x": viewer.context.getCamera().position.x,
                "y": viewer.context.getCamera().position.y,
                "z": viewer.context.getCamera().position.z
            }

            socket.emit('camera_move', cameraPos);
        })
    }
}
```

### Little styling

We will add basic styling for Connection form and Labels that will represent the position

```css
.label 
{
    color: #FFF;
    font-family: sans-serif;
    padding: 2px;
    background: rgba( 0, 0, 0, .6 );
}

#socket-connection-form{
    position: fixed;
    top: 0;
    right: 0;
    padding: 20px;
    box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
    text-align: center;
    width: 200px;
    display: inline-block;
    background: white;
}
#socket-connection-form>label{
    font-size: 18px;
    padding: 4px;
    font-family: Arial, Helvetica, sans-serif;
}
#socket-connection-form>input{
    margin-top: 10px;
    font-size: 18px;
    padding: 4px;
    font-family: Arial, Helvetica, sans-serif;
    width: 100%;
    margin-bottom: 14px;
}
#socket-connection-form>button{
    padding: 12px;
    border: unset;
    background: #f57c00;
    border-radius: 8px;
    width: 100%;
    font-size: 18px;
}
#socket-connection-form>button:hover{
    box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
    transition: 0.2s;
}
```

## The result

Here is an example of everything we've learned today:

[Github repo](https://github.com/aka-blackboots/hello-world/tree/main/examples/web-ifc-viewer/socket-io/)

## Next steps

Congrats! Now you know how to use **Socket.IO** to share the User's Camera position, now you can perform variety of Operations and Share those over network!

## IFC to gLTF

web-ifc-viewer is a 3D BIM viewer. From its vast set of tools, converting IFC to gLTF is one useful tool. This tutorial will guide you step by step how you can upload IFC file and get them converted to gLTF along with the relevant properties.

You can find the complete source of the export functionality [here](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-viewer/gltf-export) and source code of import functionality [here](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-viewer/gltf-import)

* Using IFC.js requires a basic knowledge of web development (HTML, CSS, JavaScript) and Three.js. If you have no previous experience with Three.js, you should probably look [here](https://threejs.org/manual/).

## Setting up the project

Before diving in deep, it is recommended that you have your **Two Projects** created one which will be used for **Exporting IFC to gLTF** and other for **Viewing gLTF Files**.

You can use this [section](https://ifcjs.github.io/info/docs/Guide/web-ifc-viewer/Introduction#setting-up-3d-scene-web-ifc-viewer). Don't worry! it is just boiler plate code for getting web-ifc-viewer running.

We will divide this tutorial into two sections as well, first for exporting and later for importing.

## 1. IFC to gLTF

### Importing Dependencies

```javascript
import {
        IFCWALL,
        IFCWALLSTANDARDCASE,
        IFCSLAB,
        IFCWINDOW,
        IFCMEMBER,
        IFCPLATE,
        IFCCURTAINWALL,
        IFCDOOR} from 'web-ifc';
```

### Conversion

The next step is to add function call `onchange` of input in `app.js`

* Whenever input tag is clicked upon we will call `loadIfc`

```javascript
const input = document.getElementById('file-input');
input.onchange = loadIfc;

async function loadIfc(event) {
    // IFC to gLTF conversion will happen here
    ...
    }
```

**Next**, we will work on conversion

* Creating URL from File Object

* Using `exportIfcFileAsGltf` and passing config to it to get relevant gLTF files.

* If we pass `splitByFloors` as true the `result` we get will have gLTF files separated according to Floors.

* `categories` are used to get gLTF files for specific IFC elements, we will pass the imported `IFC types` here.

* Setting `getProperties` as `true` generates a .json file which has the relevant properties stored in it.
  
* Getting the outcome of `exportIfcFileAsGltf()` in `result`

```javascript
async function loadIfc(event) {
    const file = event.target.files[0];
    const url = URL.createObjectURL(file);

    const result = await viewer.GLTF.exportIfcFileAsGltf({
        ifcFileUrl: url,
        splitByFloors: true,
        categories: {
            walls: [IFCWALL, IFCWALLSTANDARDCASE],
            slabs: [IFCSLAB],
            windows: [IFCWINDOW],
            curtainwalls: [IFCMEMBER, IFCPLATE, IFCCURTAINWALL],
            doors: [IFCDOOR]
        },
        getProperties: true
    });

    // Using Result and Downloading gLTF files

    // Creating Link Tag
    const link = document.createElement('a');
    document.body.appendChild(link);

    // Looping in result
    for(const categoryName in result.gltf) {
        const category = result.gltf[categoryName];

        // Looping in Category according to Levels
        for(const levelName in category) {
            const file = category[levelName].file;

            // If file is present for a level under category we will download it
            if(file) {
                // Downloading gLTF file in local machine
                link.download = `${file.name}_${categoryName}_${levelName}.gltf`;
                link.href = URL.createObjectURL(file);
                link.click();
            }
        }
    }

    // We will check for Properties in result and download the JSON file for it
    for(let jsonFile of result.json) {
        link.download = `${jsonFile.name}.json`;
        link.href = URL.createObjectURL(jsonFile);
        link.click();
    }

    // Removing the Node created for link
    link.remove();
}
```

### Let's try it

If you did everything right, you should see something like below. This will download bunch of gLTF files.

## 2. gLTF Viewer

Now we have gLTF files and Properties file with us, we will use these files and show the model in `web-ifc-viewer`. We will use another project for this.

### Loading gLTF files

* Loading gLTF models using `viewer.GLTF.loadModel()`

* Getting Properties from `properties.json`

* Creating Spatial Tree

```javascript
let properties;

async function load() {
    // Load geometry
    await viewer.IFC.setWasmPath('../../../');
    await viewer.GLTF.loadModel('../../../GLTF/doors_Nivel 1.gltf');
    await viewer.GLTF.loadModel('../../../GLTF/slabs_Nivel 1.gltf');
    await viewer.GLTF.loadModel('../../../GLTF/slabs_Nivel 2.gltf');
    await viewer.GLTF.loadModel('../../../GLTF/walls_Nivel 1.gltf');
    await viewer.GLTF.loadModel('../../../GLTF/windows_Nivel 1.gltf');
    await viewer.GLTF.loadModel('../../../GLTF/curtainwalls_Nivel 1.gltf');

    // Load properties
    const rawProperties = await fetch('../../../GLTF/properties.json');
    properties = await rawProperties.json();

    // Get spatial tree
    const tree = await constructSpatialTree();
    console.log(tree);
}

load();
```

### Creating Spatial Tree

* Creating Project Node using Object of `IFCPROJECT`

* Getting Relationships and contructing Spatial Tree Node and Passing back this structure

* `constructSpatialTreeNode` is a recursive function which will be used to generate the data accordingly

```javascript
// Get spatial tree
async function constructSpatialTree() {
    // Getting Project Properties 
    const ifcProject = getFirstItemOfType('IFCPROJECT');

    // Creating Project Node
    const ifcProjectNode = {
        expressID: ifcProject.expressID,
        type: 'IFCPROJECT',
        children: [],
    };

    const relContained = getAllItemsOfType('IFCRELAGGREGATES');
    const relSpatial = getAllItemsOfType('IFCRELCONTAINEDINSPATIALSTRUCTURE');

    await constructSpatialTreeNode(
        ifcProjectNode,
        relContained,
        relSpatial,
    );

    return ifcProjectNode;
}

// Utils functions
function getFirstItemOfType(type) {
    return Object.values(properties).find(item => item.type === type);
}

function getAllItemsOfType(type) {
    return Object.values(properties).filter(item => item.type === type);
}

// Recursively constructs the spatial tree
async function constructSpatialTreeNode(
    item,
    contains,
    spatials,
) {
    const spatialRels = spatials.filter(
        rel => rel.RelatingStructure === item.expressID,
    );
    const containsRels = contains.filter(
        rel => rel.RelatingObject === item.expressID,
    );

    const spatialRelsIDs = [];
    spatialRels.forEach(rel => spatialRelsIDs.push(...rel.RelatedElements));

    const containsRelsIDs = [];
    containsRels.forEach(rel => containsRelsIDs.push(...rel.RelatedObjects));

    const childrenIDs = [...spatialRelsIDs, ...containsRelsIDs];

    const children = [];
    // Looping through the child elements and creating populating values for it
    for (let i = 0; i < childrenIDs.length; i++) {
        const childID = childrenIDs[i];
        const props = properties[childID];
        const child = {
            expressID: props.expressID,
            type: props.type,
            children: [],
        };

        // For Every child element repeating the step and pushing it to children array
        await constructSpatialTreeNode(child, contains, spatials);
        children.push(child);
    }

    item.children = children;
}
```

### Getting Properties

With major steps done, now we will get properties of elements on double click. Let's dive in!

* Using `id` we will get the properties and then get property sets for it

```javascript
window.ondblclick = async () => {
    const result = await viewer.IFC.selector.pickIfcItem(true);
    const foundProperties = properties[result.id];
    getPropertySets(foundProperties);
    console.log(foundProperties);
};

function getPropertySets(props) {
    const id = props.expressID;
    const propertyValues = Object.values(properties);
    const allPsetsRels = propertyValues.filter(item => item.type === 'IFCRELDEFINESBYPROPERTIES');
    const relatedPsetsRels = allPsetsRels.filter(item => item.RelatedObjects.includes(id));
    const psets = relatedPsetsRels.map(item => properties[item.RelatingPropertyDefinition]);
    for(let pset of psets) {
        pset.HasProperty = pset.HasProperties.map(id => properties[id]);
    }
    props.psets = psets;
}
```

### Lets try it

If everything went right, the output will look as below

## Conclusion

Congratulations! You have successfully exported IFC file as gLTF files and have a viewer for it. Go to the next pages of the docs to find out what else can you do with IFC.js.

## Memory

* You can follow along with the full example on [Github](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-viewer/memory).

You have both freedom and responsibility when it comes to **memory management** in your IFC.js app. Fortunately, IFC.js lets you balance these to **release memory** very easily. Let's see how it's done.

* IFC.js builds upon the Three.js **dispose()** function. See how IFC.js does it [here](https://github.com/IFCjs/web-ifc-viewer/blob/master/viewer/src/ifc-viewer-api.ts#L220) and [here](https://github.com/IFCjs/web-ifc-three/blob/main/web-ifc-three/src/IFC/components/MemoryCleaner.ts), and also read what Three.js [has to say](https://threejs.org/docs/#manual/en/introduction/How-to-dispose-of-objects).

## How to do it

### Monitoring the memory

[stats.js](https://github.com/mrdoob/stats.js/) is a library to **monitor the memory and performance** of your Three.js app, made by the creator of Three.js himself. Let's go ahead and install with `npm i stats.js`, **import, initialize and attach it** to our viewer.

```javascript
import Stats from "stats.js/src/Stats";

const stats = new Stats();
addStats();

function addStats() {
    stats.showPanel(2);
    document.body.append(stats.dom);
    viewer.context.stats = stats;
};
```

During development we don't have to second guess our memory management anymore, because now it's **visualized** for us.

* If you don't remember how to setup your viewer, just look at the [full example](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-viewer/memory) or at previous tutorials.

### Load up the model

First we'll **create** an HTML **input button** and use `loadIfc()` to load our models from file. Style as you wish!

```html
<input type="file" id="input-button" />
```

```javascript
async function loadIfcFromFile(file) {
  const model = await viewer.IFC.loadIfc(file, true);
}
```

* We call [loadIfc()](https://github.com/IFCjs/web-ifc-viewer/blob/master/viewer/src/components/ifc/ifc-manager.ts#L42/) when a user loads an IFC file. Internally, it creates a URL then calls [loadIfcUrl()](https://github.com/IFCjs/web-ifc-viewer/blob/master/viewer/src/components/ifc/ifc-manager.ts#L53/) for us.

Now **link** the button and the function.

```javascript
const input_button = document.getElementById("input-button");
input_button.addEventListener("input", (input) => {
  loadIfcFromFile(input.target.files[0])},
  false
);
```

So that we can load and release the same model over and over, for this example we'll add a tiny hack to reset the DOM event.

```javascript
input_button.addEventListener("click", (e) => {
  e.target.value = "";
});
```

### Dispose memory

Finally let's create our function to **dispose** memory on command using `dispose()`. Here's how it's done:

```javascript
function releaseMemory() {
  viewer.dispose();
  viewer = null;
  viewer = new IfcViewerAPI({ container });
  viewer.IFC.setWasmPath("../../../");
  addStats();
}
```

Keep in mind: Once we call `dispose()`, we need to **re-initialize** our viewer instance (and Stats module)

For this example let's attach our function to a new HTML button.

```html
<input type="button" id="release-button" value="Release Memory" />
```

```javascript
const release_button = document.getElementById("release-button");
release_button.addEventListener("click", () => releaseMemory());
```

Try loading a model and releasing the memory: you'll notice our model disappears and our visualizer confirms this. Remember that it **might take time** for the garbage collector to do its job.

* We have [test files](https://github.com/IFCjs/test-ifc-files) for you to try out different models.

## The result

This is how the application looks like:

[Github repo](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc-viewer/memory/)

## Next steps

Congratulations! Your IFC.js apps are now **free of memory leaks**. This memory management will keep your app squeaky clean and running smooth.

## web-ifc-viewer-API

The API is documented, so when you use any of the objects or methods listed in this documentation, you should see help from Intellisense, regardless of the IDE you're using. [Check it out!](https://github.com/IFCjs/web-ifc-viewer/blob/master/viewer/src/components/ifc/ifc-manager.ts).

However, we realize that with Intellisense or comments it is not the most comfortable. On this page we will give an overview of what the API can do. We can see it in operation in detail in the specific tutorials section below.

## IfcViewerAPI

We import the object from the library. You can use the loadIfc() method to load IFC from a URL. For example to load an IFC we can do it as follows.

```javascript
import { IfcViewerAPI } from "web-ifc-viewer";

const viewer = new IfcViewerAPI();

const input = document.getElementById("file-input");
input.addEventListener(
    "change",
    (changed) => {
    const file = changed.target.files[0];
    const url = URL.createObjectURL(file);
    const model = await viewer.IFC.loadIfcUrl(url)
})
```

Later we will review the details of how to use the different methods dedicated to load files.

Many of the API operations run on a specific model. We will use ModelID to express on which model we want to operate.

You can get the id of a model through the modelID property.

```javascript
const modelID = IfcViewerAPI.IFC.ifcModel.modelID;
```

## Setup

### setWasmPath

```javascript
async IfcViewerAPI.IFC.setWasmPath(../../../)
```

Specifies the location of the web-ifc.wasm and web-ifc-mt.wasm files. These files are required to build any application with IFC.js. You can find them in node_modules/web-ifc/.

* Be careful with your tools!!: If you use frameworks or libraries like React, Angular, Vue or Svelte it is possible that the root path of the project doesn't correspond to the root path of the served application. You will have to check in [each case](https://github.com/IFCjs/examples) how the paths of the statically served files are managed.

#### Arguments:

* `path`: Route of `web-ifc.wasm`.

#### Example:

```javascript
await IfcViewerAPI.IFC.setWasmPath(dist / wasmDir);
```

When `web-ifc.wasm` is in `dis/wasmDir`.

## Tools

### addClippingPlane

```javascript
IfcViewerAPI.clipper.createPlane();
```

#### Example:

```javascript
window.onkeydown = (event) => {
  if (event.code === "KeyP") {
    IfcViewerAPI.clipper.createPlane();
  }
};
```

Adds a clipping plane on the face the cursor is pointing at.

### removeClippingPlane

```javascript
IfcViewerAPI.clipper.deletePlane();
```

#### Example:

```javascript
window.onkeydown = (event) => {
  if (event.code === "KeyO") {
    IfcViewerAPI.clipper.deletePlane();
  }
};
```

Deletes the clipping plane pointed at by the cursor.

### toggleClippingPlane

```javascript
IfcViewerAPI.clipper.toggle();
```

#### Example:

```javascript
IfcViewerAPI.clipper.toggle();
```

Turns all clipping planes on/off.

### openDropboxWindow

```javascript
this.dropbox.loadDropboxIfc();
```

#### Example:

```javascript
IfcViewerAPI.dropbox.loadDropboxIfc();
```

Opens a dropdown window where the user can select their IFC models.

### loadIfc

```javascript
IfcViewerAPI.IFC.loadIfc(file: File,
                         fitToFrame: boolean)
```

#### Arguments:

* `file`: IFC as `File`.

* `fitToFrame`: If `true`, brings the `perspectiveCamera` to the loaded IFC.

#### Example:

```javascript
const input = document.getElementById('file-input')
input.addEventListener('change', changed => {
    const file = changed.target.files[0]
    const model = await IfcViewerAPI.IFC.loadIfcUrl(file)
})
```

Loads the given IFC in the current scene.

### loadIfcUrl

```javascript
IfcViewerAPI.IFC.loadIfcUrl(url: string,
                           fitToFrame: boolean,
                            onProgress: any,
                            onError: any)
```

#### Arguments:

* `file`: Ifc as `url`.

* `fitToFrame`: If `true`, brings the `perspectiveCamera` to the loaded IFC.

* `onProgress`: A callback function to report on downloading progress.

* `onError`: A callback function to report on loading errors.

#### Example:

```javascript
const input = document.getElementById("file-input");
input.addEventListener(
    "change",
    (changed) => {
    const file = changed.target.files[0];
    const url = URL.createObjectURL(file);
    const model = await IfcViewerAPI.IFC.loadIfcUrl(url)
})
```

Load the Ifc from a `URL.createObjectURL` and add it to the scene.

### addGrid

```javascript
IfcViewerAPI.grid.setGrid(size: number, divisions: number,
                          colorCenterLine: Color, colorGrid: Color)
```

#### Arguments:

* `size`: Grid `size`.

* `divisions`: Number of `divisions` in `X` & `Y`.

* `colorCenterLine`: Color of the `X` & `Y` center lines of the `grid`.

* `colorGrid`: Color of lines `X` & `Y` of the `grid`.

#### Example:

```javascript
IfcViewerAPI.grid.setGrid(40);
```

Using `size` resizes the size of the mesh in X and Y.

```javascript
IfcViewerAPI.grid.division(20);
```

Using `division` configure the number of divisions in `X` & `Y`.

```javascript
IfcViewerAPI.grid.colorCenterLine(0x0000ff);
```

Using `colorCenterLine` can change the color of the central lines in the grid X & Y.

```javascript
IfcViewerAPI.grid.colorGrid(0x008000);
```

Using `colorGrid` can change the color of lines `X` & `Y` of the grid.

* Add a base `mesh` to the scene: "GridHelper" [Check it out!](https://threejs.org/docs/#api/en/helpers/GridHelper)

### addAxes

```javascript
IfcViewerAPI.axes.setAxes(size: number)
```

#### Arguments:

* `size`: `size` of `axes`.

#### Example:

```javascript
IfcViewerAPI.grid.setAxes(20);
```

Using `size` define the length of the `axes` on which the `ifcModel` is loaded.

* Add axes to the scene: "AxesHelper" [Check it out!](https://threejs.org/docs/#api/en/helpers/AxesHelper)

### getModelID

```javascript
IfcViewerAPI.IFC.getModelID() : number
```

#### Example:

```javascript
const modelID = await IfcViewerAPI.IFC.ifcModel.modelID;
```

Gets the Id of the model selected with the cursor.

### getProperties

```javascript
IfcViewerAPI.IFC.getProperties(modelID: number, id: number,
                                indirect: boolean)
```

#### Arguments:

* `modelID`: `id` of model IFC.

* `id`: Express IDs of the item.

* `indirect`: is `true`? If `true`, also returns `psets`, `qsets` and type properties.

#### Example:

```javascript
const properties = await IfcViewerAPI.IFC.getProperties(modelID, id, true);
```

Get the properties of a specified item.

### getSpatialStructure

```javascript
IfcViewer.IFC.getSpatialStructure(modelID: number): any
```

#### Arguments:

* `modelID`: `id` of model IFC.

#### Example:

```javascript
const structure = await IfcViewerAPI.IFC.getSpatialStructure(modelID);
```

Gets the spatial structure of the specified model.

### getAllItemsOfType

```javascript
IfcViewerAPI.IFC.getAllItemsOfType(modelID: number, type: number,
                                    verbose: boolean): any
```

#### Arguments:

* `modelID`: `id` of model IFC.

* `type`: Type of element. You can import the `type` from `web-ifc`.

* `verbose`: Is `true`? So you get the properties of all the elements.

#### Example:

```javascript
const modelID = await IfcViewerAPI.IFC.ifcModel.modelID;
IfcViewerAPI.IFC.getAllItemsOfType(modelID, 3, true);
```

Get all elements of the specified type in the specified IFC model.

### prePickIfcItem

```javascript
IfcViewerAPI.IFC.selector.prePickIfcItem();
```

#### Example:

```javascript
window.onmousemove = () => IfcViewerAPI.IFC.selector.prePickIfcItem();
```

Highlights the item pointed by the cursor.

### pickIfcItem

```javascript
IfcViewerAPI.IFC.selector.pickIfcItem(focusSelection: boolean):
 {modelID: number, id: number}
```

#### Arguments:

* `focusSelection`: If `true`, animate the `perspectiveCamera` to focus the current selection.

#### Example:

```js
window.ondblclick = () => IfcViewerAPI.IFC.selector.pickIfcItem(true);
```

Highlights the element pointed at by the cursor and gets its properties.

### pickIfcItemsByID

```js
IfcViewerAPI.IFC.selector.pickIfcItemsByID(modelID: number, ids: number
                                            focusSelection: boolean)
```

#### Arguments:

* `modelID`: `id` of model IFC.

* `id`: Express IDs of the item.

* `focusSelection`: If `true`, animate the `perspectiveCamera` to focus the current selection.

#### Example:

```javascript
const modelID = await IfcViewerAPI.IFC.ifcModel.modelID;
const pickID = await IfcViewerAPI.IFC.selector.pickIfcItemsByID(modelID, 0, true);
```

Highlights the item with the given ID with the picking material.

Remember this...

### dispose

```javascript
IfcViewerAPI.dispose();
```

* When to use dispose: Use this only when removing the **ifcViewerAPI** instance. This is especially important when using libraries and frameworks that handle the object lifecycle automatically. (eg React, Angular, etc.) If you're using one of these examples and you're instantiating `-ifc-viewer-api` inside a component make sure you use this method on the component for destruction.

> 출처: https://ifcjs.github.io/info/docs/Introduction/
