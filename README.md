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

```
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

```
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

```
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

```
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

```
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

```
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

```
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

```
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

```
ifcLoader.ifcManager.setWasmPath("static/wasm/");
```

모두 제대로 했다면, 로컬 서버에서 [이것](https://ifcjs.github.io/hello-world/examples/web-ifc-three/helloworld/)과 비슷한 뭔가를 보게 될 것입니다. 이제부터는 가능성이 무궁무진합니다.

### 모델 로드하기

앞에서는 BIM 모델을 직접 로드하는 방법을 보여 드렸습니다. 아주 훌륭했습니다. 만약 사용자가 업로드하는 것을 허용하지 않고 대신 저희의 BIM 모델들을 보여주고 싶다면? 이는 매우 간단합니다. 일반적으로 2가지 방법이 있습니다:

* 보여주고자 하는 IFC 파일을 애플리케이션과 동일한 곳에 두기.

* 보여주고자 하는 IFC 파일을 외부 저장소로부터 가져오기.

1번째의 경우 IFC 파일의 URL을 참조하는 것으로 충분합니다. 즉, 애플리케이션의 상대 경로를 이용하는 것입니다. 예를 들어, IFC 파일이 프로젝트의 루트에 있는 "models" 폴더 안에 있다면 애플리케이션을 시작할 때 다음과 같이 IFC를 로드할 수 있습니다:

```
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

## Web-ifc guide

**web-ifc** is a javascript library to read and write ifc files, at native speeds. **web-ifc** is part of the [ifc.js](https://ifcjs.github.io/info/) project, which aims to lower the threshold for developing open BIM applications.

### But I know nothing about the project!

Don't worry: if you want to participate, we will give **top priority to your onboarding** so that you can start using the library right away and help us with whatever you want.

## Cloning the repository locally

The first thing to do is to clone the repository to your local machine.
Start by forking the project (click on fork button on the top right) and choosing yourself as the owner of the fork (if asked).
Now go to the forked repository, click on code button (generally green in color) and copy the https URL.

Now open terminal on your machine and change the current working directory to the location where you want to clone the directory. Enter these commands:

```
// Type git clone, and then paste the URL you copied earlier like this
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY

// change the current directory and enter the cloned repository using cd, and then name of the repository like this
cd web-ifc

// Using git checkout -b will create a new branch and immediately switch to it
git checkout -b ＜new-branch-name＞
// <new-branch-name> -> name your branch exactly same as the bounty name or the name starts with bounty ID

// Minimise this terminal instead of closing it
```

## Setting up the project

### Build it locally

```
// To install web-ifc
npm install web-ifc
```

## Quick setup

```
//Use these in your project whenever needed not in the terminal right now
const WebIFC = require("web-ifc/web-ifc-api.js");

// initialize the API
const ifcApi = new WebIFC.IfcAPI();

// initialize the library
await ifcApi.Init();

// open a model from data
let modelID = ifcApi.OpenModel(/* IFC data as a string or UInt8Array */, /* optional settings object */, );

// the model is now loaded! use modelID to fetch geometry or properties
// checkout examples/usage for some details on how to read/write IFC

// close the model, all memory is freed
ifcApi.CloseModel(modelID);
```

See [examples](https://github.com/tomvandig/web-ifc/tree/main/examples/usage/src) for more details on how to use web-ifc.

## Building WASM module

### Setting up emscripten

The WASM library is built through emscripten, please see [the emscripten installation guide](https://emscripten.org/docs/getting_started/downloads.html) for information on how to set up emscripten. Afterwards `emsdk_env` needs to be in your path(environment variable).

### WASM library

Open the terminal again and run these commands:

Run `npm install` to install all dependencies.
Run `npm run setup-env` whenever you open a new terminal, this will set up the required emscripten environment variables for you to compile code.
Run `npm run build-release-all` to build a release version of the wasm binary and the accompanying web-ifc api. It will be placed in ./dist.
Run `npm run dev` to launch a development server with a basic ifc file viewer.

## Writing code on it

### Using an IDE (Integrated Development Environment)#

VS Code - You can install VS Code from [here](https://code.visualstudio.com/download).

### Compiler for code

GCC with MinGW (for windows) - You can configure GCC C++ compiler from [here](https://code.visualstudio.com/docs/cpp/config-mingw). Clang (for macOS) - You can configure Clang compiler from [here](https://code.visualstudio.com/docs/cpp/config-clang-mac).

Although the primary focus of the library is to be used through WebAssembly in the browser/nodejs, the project can be used stand-alone as a c++ library or executable. See [here](https://github.com/tomvandig/web-ifc/blob/main/src/wasm/web-ifc-test.cpp) for a simple entry point to get started.

## Creating a submit pull request

Open you terminal and enter these commands:

use `git status` to review your changes.
use `git checkout master` to checkout to master branch.
use `git pull` to sync your cloned repository with the origin repository.
use `git checkout <branch-name>` to go back to your working branch.
use `git pull` to sync with the the main branch.
use `git add .` to stage your changes.
use `git commit -m "type a message to display for changes"` to commit the changes made.
use `git push` to push the changes to the main repository.

Now go to your github, inside the forked version of the repository. You will see a notification on the right (if not click on pull requests) 'compare & pull request' (generally green color button), click on it. Now describe the changes you made in short and click on 'create pull request'.

### How do I get started?

[Talk to us!](https://discord.gg/FXfyR4XrKT) Tell us about your situation and your ideas and we will help you get started as soon as possible.
  
## Introduction

### Full IFC control at native speed

It is often thought that web applications are not as powerful as desktop applications. Relatively recently, however, [WebAssembly](https://webassembly.org/) appeared on the scene.

* WebAssembly is a technology that allows the use of languages like C++ to create web applications.

This means we can have the best of both worlds: the **flexibility** of a web application and the **full performance** of a machine. And this is what web-ifc is all about. You can install it with `npm i web-ifc` or `yarn add web-ifc` and it has the following features:

* It is as **fast** as native applications thanks to its parsing core, written from scratch in C++.

* It can be run directly on the **client** or as a **backend service**. Bring BIM to all parts of your system!

* It can read **100% of the IFC data, including IFC types**. This allows data to be easily extracted, structured, traversed and entered into databases.

* It can **edit data and write entire IFCs from scratch**. Create apps that communicate with the large software vendors.

In the following points, the API and its functionalities will be shown step by step. However, there are a **some issues** that are important to be clear about before using `web-ifc`.

### But wait, I don't know C++!

Don't worry! Although the parser is written in C++, it is compiled in a file called `web-ifc.wasm` that **browsers understand automatically**. Just include this file in your application and you will have access to the full API with native speed with **JavaScript** or **TypeScript**. How cool is that?

### What is the .wasm file for?

The web-ifc.wasm file contains the IFC **parsing core**. It is pre-compiled and **hyper-efficient**; unlike JavaScript, which has to be compiled line by line, this file can be sent directly to the CPU and executed without prior interpretation.

You can find this file in the `node-modules/web-ifc/web-ifc.wasm` folder. You will need to serve this file with your application (if frontend) or have it on your server (if backend).

* Beware: when you update the web-ifc version in your application, you will also have to update (copy) the corresponding version of web-ifc.wasm.

### When should I use web-ifc?

`Web-ifc` is the **lightest** and **most flexible** module of IFC.js. However, this flexibility also means that you have to know what you are doing, and therefore know the internals of the IFC schema relatively well.

Moreover, web-ifc **does not implement a 3d viewer**. This is an advantage, because it means that you can get IFC geometry without relying on a particular 3d renderer in a more agile way.

* If you want to see 3d geometry easily, you will either have to implement it yourself, or use **web-ifc-three** or **web-ifc-viewer**.

## Hello World

## Introduction

Web-ifc provides an easy way to read and manipulate your ifc file. you can as example to get the spatial tree information or project, geometries, add new entities etc... In this tutorial we will **Load an ifc file** and **Retrieves all its IFCSPACE**.

Thanks to web-ifc all of these are just a breeze

* You can get the full code [here](https://github.com/ifcjs/hello-world/tree/main/examples/web-ifc/hello-world).

## Setting up the project

Node JS must be install on your machine, and to makes thing easier i recommand to use Visual Code studio with the plugin Live server.

### install dependencies

```
npm init
npm install web-ifc
npm install rollup --save-dev
npm install @rollup/plugin-node-resolve --save-dev
npm install @open-wc/building-rollup --save-dev
```

### add scripts in your package.json

open your package.json and add aliases build and watch in the scripts section,

```
  "scripts": {
    "build": "rollup -c ./rollup.config.js",
    "watch": "rollup -w -c ./rollup.config.js"
  },
```

### configure Rollup

on your project root add a config file **rollup.config.js** with these configs values:

```
import resolve from "@rollup/plugin-node-resolve";

export default {
  input: "app.js",
  output: [

    {
      format: "esm",
      file: "bundle.js",
    },
  ],
  plugins: [resolve()],
};
```

## Feed your root folder :)

To make things easier we drop all in the root folder :

* app.js
* index.html
* drop an .ifc file of your choice for testing.
* copy **web-ifc-mt.wasm** and **web-ifc.wasm** from **node_modules/web-ifc** here in the root folder

### Serving files from a server

for Visual code studio lovers there is an extension which remove all headaches, this will give you the possibility to serve your bundled app. elsewhere you can run your code throught node server directly

https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer

## How to do it

Ok now you've got your folder ready to start, let's complete these 2 objectives :

* load your ifc file

* grab some datas from this loaded ifc file

### get an .ifc file

If you don't have a sample ifcModel you can grab one from [here](https://github.com/IFCjs/test-ifc-files)

### index.html

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WEB-IFC</title>
</head>
<body>
  <div id="main">
      <div id="result"></div>
  </div>
  <script src="bundle.js"></script>
</body>
</html>
```

### app.js

#### definitions

We will only need **web-ifc/web-ifc-api** just pay attention on ifcFileLocation its an ifcModel stored in the root folder in this demo.

```
import {IfcAPI} from "web-ifc/web-ifc-api";
const ifcFileLocation = "duplex-apartment.ifc"; // dont forget to modify for your ifc filename
let modelID = 0;
const ifcapi = new IfcAPI();
//ifcapi.SetWasmPath("./wasm/"); only if the wasm file are note at the same level as app.js
```

#### fetching ifcFile function

i've chosen the XMLHttpRequest to fetch my file you can chose any method of your choice. The only required thing is `new Uint8Array(oReq.response)` at the end.

```
/**
 * resolve a Uint8Array().
 * 
 * @param string url location of your ifc file
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

#### loadFile with Web-ifc

We are almost done ;) . ifcapi is initialized we fetch our ifcFile and with ifcapi we can work with the loaded file

```
ifcapi.Init().then(()=>{
  getIfcFile(ifcFileLocation).then((ifcData) => {
    modelID = ifcapi.OpenModel(ifcData);
    let isModelOpened = ifcapi.IsModelOpen(modelID);
    console.log({isModelOpened});
    ifcapi.CloseModel(modelID);
  });
});
```

#### Let's Build

run this command before opening your app **npm run build** rollup will build your app and then you will have to serve your app. If you have live server extension installed on Visual code studio you can simply run it and go to the hello_world example. At any code changes don't forget to rebuild OR you can use **npm run watch** while the job is not done rollup will rebuild on code save

if in your console you got this message `{isModelOpened: true}`

**congratulations**

All is setup and running but now i want **ALL** IFCSPACES

###Retrieve a list of spaces.

Okay, now i want to get all the IFCSPACES and display them somewhere. Lets make a function wich grab all IFCSPACE. You can fetch by any type you need. i've made a total arbitrary decision to take IFCSPACE.

```
/**
 * Get all IFCSPACE from ifc file
 * @param integer modelID 
 * @returns array
 */
function getAllSpaces(modelID) {
    // Get all the propertyset lines in the IFC file
    let lines = ifcapi.GetLineIDsWithType(modelID, IFCSPACE);
    let lineSize = lines.size();
    let spaces = [];
    for (let i = 0; i < lineSize; i++) {
        // Getting the ElementID from Lines
        let relatedID = lines.get(i);
        // Getting Element Data using the relatedID
        let relDefProps = ifcapi.GetLine(modelID, relatedID);
        spaces.push(relDefProps);

    }
    return spaces;
}
```

If your attentive you will notice the const IFSPACE from **let lines = ifcapi.GetLineIDsWithType(modelID, IFCSPACE);** it means I want to get all IFCSPACE from my ifc file. Don't forget to import this as follow.

```
import {IfcAPI,IFCSPACE} from "web-ifc/web-ifc-api";
```

#### call getAllSpaces

after the .ifc file has been retrieved and loaded in ifcapi i can call my function to get all spaces.

```
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

## Next steps

**congratulations** you can load your .ifc file and find any element you want. However it could be nice to navigate in your spatial tree, or describe an IFCSPACE... To be continued

## Editing Properties

?

## Properties

?

## web-ifc-API

?

---

# web-ifc-three

## Introduction

?

## Setup

?

## API

?

## Picking

?

## Subsets

?

## Properties

?

## Hiding

?

## Memory

?

## Multithreading

?

## Mapbox

?

---

# web-ifc-viewer

## Contribute

?

## Introduction

?

## Json Property

?

## Picking

?

## Socket.IO

?

## IFC to gLTF

?

## Memory

?

## web-ifc-viewer-API

?

> 출처: https://ifcjs.github.io/info/docs/Introduction/
