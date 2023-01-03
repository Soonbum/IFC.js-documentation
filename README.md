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

## Web-ifc 가이드

**web-ifc**는 네이티브 속도로 ifc 파일을 읽고 쓸 수 있는 자바스크립트 라이브러리입니다. **web-ifc**는 [ifc.js](https://ifcjs.github.io/info/) 프로젝트의 일부입니다. 이 프로젝트는 개방형 BIM 애플리케이션을 개발하기 위한 문턱을 낮추는 데 목적을 두고 있습니다.

### 하지만 나는 프로젝트에 대해 아무 것도 모릅니다!

걱정하지 마십시오: 만약 참여를 원하신다면 **당신의 onboarding을 최우선으로 고려하여** 당신이 라이브러리를 바로 사용할 수 있게 해주고 당신이 원하는 것으로 저희를 도우실 수 있습니다.

## 로컬에 리포지토리 클로닝(Cloning)하기

1번째로 해야 할 것은 당신의 로컬 머신에 리포지토리를 클론을 만드는 것입니다.
(우상단의 fork 버튼을 클릭하여) 프로젝트를 포크(fork)하여 시작하시고 (만약 물어본다면) 포크의 소유자를 당신 자신으로 선택하십시오.
이제 포크된 리포지토리로 가서 (일반적으로 녹색으로 된) 코드(code) 버튼을 클릭하시고 https URL을 복사하십시오.

이제 당신의 머신에서 터미널을 여시고 현재 작업 디렉토리를 복제하고 싶은 디렉토리로 변경하십시오. 다음 커맨드들을 입력하십시오:

```
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

```
// web-ifc 설치하기
npm install web-ifc
```

## 빠른 설정

```
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

```
npm init
npm install web-ifc
npm install rollup --save-dev
npm install @rollup/plugin-node-resolve --save-dev
npm install @open-wc/building-rollup --save-dev
```

### package.json에 스크립트 추가하기

package.json을 열고 scripts 섹션에 build와 watch라는 이름을 추가합니다.

```
  "scripts": {
    "build": "rollup -c ./rollup.config.js",
    "watch": "rollup -w -c ./rollup.config.js"
  },
```

### Rollup 구성하기

프로젝트 루트에 구성 파일 **rollup.config.js**를 추가하십시오. 구성 파일의 내용은 다음과 같습니다:

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

#### 정의

**web-ifc/web-ifc-api**만 필요합니다. ifcFileLocation만 신경쓰시면 됩니다. 이 데모에서 루트 폴더에 저장된 ifcModel입니다.

```
import {IfcAPI} from "web-ifc/web-ifc-api";
const ifcFileLocation = "duplex-apartment.ifc"; // 당신의 ifc 파일명으로 변경하는 것을 명심하세요
let modelID = 0;
const ifcapi = new IfcAPI();
ifcapi.SetWasmPath("./wasm/"); // wasm 파일이 app.js와 같은 레벨에 있는 노트일 경우에만
```

#### ifcFile 함수 가져오기

파일을 가져오기 위해 XMLHttpRequest를 선택했습니다. 당신이 원하는 아무 방식을 선택하셔도 됩니다. 마지막에 필요한 것은 `new Uint8Array(oReq.response)` 뿐입니다.

```
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

#### 빌드해 봅시다.

앱을 열기 전에 커맨드 **npm run build**를 실행하십시오. rollup이 앱을 빌드할 것입니다. 그리고 나서 앱을 제공할 수 있게 됩니다. 만약 Visual Studio Code에 live server 확장이 설치되어 있다면 그저 실행해서 hello_world 예제로 갈 수 있습니다. 코드가 변경되면 다시 빌드하는 것을 잊지 마십시오. 그렇지 않으면 작업이 완료되지 전에 **npm run watch**를 사용할 수 있습니다. rollup은 코드가 저장될 때 다시 빌드할 것입니다.

콘솔에서 다음 메시지를 보게 될 것입니다. `{isModelOpened: true}`

**축하합니다**

설정이 완료되었고 실행 중입니다. 하지만 이제 **모든** IFCSPACES를 원합니다.

### 공간 목록 가져오기

자, 이제 모든 IFCSPACES를 가져와서 어딘가에 표시하고 싶습니다. 모든 IFCSPACES를 가져오는 함수를 만들어봅시다. 원하는 어떤 타입이라도 가져올 수 있습니다. 저는 IFCSPACE를 가져오기 위해 전적으로 자의적인 결정을 내렸습니다.

```
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

```
import {IfcAPI,IFCSPACE} from "web-ifc/web-ifc-api";
```

#### getAllSpaces 호출하기

.ifc 파일을 가져온 후에 ifcapi에서 로드되면 이제 모든 공간을 가져오기 위해 나의 함수를 호출할 수 있습니다.

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

```
import {
    IfcAPI, IFCBUILDINGSTOREY
} from "web-ifc/web-ifc-api";
..

..
..
```

#### 파일 읽기

이제 파일을 읽고 [`LoadFileData()`](https://github.com/IFCjs/hello-world/blob/main/examples/web-ifc/ifc-to-json/properties/app.js#:~:text=async%20function%20LoadFile(ifcAsText))를 호출하고 IFC 데이터를 텍스트 형태로 보낼 것입니다.

```
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

```
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

```
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

```
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

```
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

```
fetch("../../../../IFC/01.ifc")
  .then((response) => response.text())
  .then((data) => {
    // 이것은 파일 데이터를 LoadFileData 메소드에 보낼 것입니다.
    LoadFileData(data);
  });
```

**요소 프로퍼티를 가져오기 위해 호출될 메소드 만들기**

**요소 데이터**를 가져오기 위한 모든 코드는 그 안에 있습니다.

```
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

```
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

```
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

```
// IFC 파일에서 모든 프로퍼티 세트 라인들을 가져옵니다.
let lines = ifcapi.GetLineIDsWithType(modelID, IFCRELDEFINESBYPROPERTIES);
```

#### 프로퍼티 세트의 ElementID 가져오기

* Lines를 가져온 후에 이것들로부터 ElementID를 가져올 것입니다. 다음에는 이 ElementID를 가지고 위에서 했던 대로 요소 데이터를 가져올 것입니다.

* 다음에는 요소 데이터를 통해 RelatedObjects를 찾아내고 만약 이 RelatedObjects 안에 프로퍼티를 찾고자 하는 ElementID가 포함되어 있다면 그것을 로컬 배열에 저장합니다.

```
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

```
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

```
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

```
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

```
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

```
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

```
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

The API is documented, so when you use any of the objects or methods listed in this documentation, you should see help from Intellisense, regardless of the IDE you're using.

We realize that with Intellisense or comments it is not the most comfortable. On this page we will give an overview of what the API can do. We can see it in operation in detail in the specific tutorials section below.

## IfcAPI

We import the object from the library. You can use the `FileReader`. Lets web applications asynchronously read the contents of files (or raw data buffers) stored on the user's computer, using File or Blob objects to specify the file or data to read.

```
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

Load an ifc file and return all the information it contains in plain text

```
const properties = IfcAPI.properties;
```

The IfcAPI class includes a property called `properties` that contains all the logic and methods regarding `properties`, `psets`, `qsets`, etc.

## Setup

### setWasmPath

```
IfcAPI.setWasmPath("../../../../");
```

Specifies the location of the web-ifc.wasm and web-ifc-mt.wasm files. These files are required to build any application with IFC.js. You can find them in node_modules/web-ifc/.

* Be careful with your tools!!: If you use frameworks or libraries like React, Angular, Vue or Svelte it is possible that the root path of the project doesn't correspond to the root path of the served application. You will have to check in [each case](https://github.com/IFCjs/examples) how the paths of the statically served files are managed.

#### Arguments:

* path: Route of `web-ifc.wasm`.

## Tools

### Init

```
IfcAPI.init(customLocateFileHandler: LocateFileHandlerFn)
```

#### Arguments:

* `customLocateFileHandler`: An optional locateFile function that let's you override the path from which the wasm module is loaded.

#### Example:

```
IfcAPI.Init();
```

Initializes the WASM module `WebIFCWasm`, required before using any other functionality

### OpenModel

```
IfcAPI.openModel(data: Uint8Array,
                 settings: LoaderSettings): number
```

#### Arguments:

* `data`: Buffer containing IFC `data`.

* `settings`: `settings` for loading the model.

#### Example:

```
IfcAPI.OpenModel(data, { LoaderSettings });
```

Opens a model and returns a modelID number

### CreateModel

```
IfcAPI.CreateModel(settings: LoaderSettings): number
```

#### Arguments:

* `settings`: Creates a new model and returns a `modelID` number.

#### Example:

```
IfcAPI.CreateModel();
```

Creates a new model and returns a modelID number.

### ExportFileAsIFC

```
IfcAPI.ExportFileAsIFC(modelID: number): Uint8Array
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`, model must no be closed.

#### Example:

```
IfcAPI.ExportFileAsIFC(modelID);
```

Exports a file to IFC using the `modelID`. Returns a `Uint8Array`

### CreateIfcGuidToExpressIdMapping

```
IfcAPI.CreateIfcGuidToExpressIdMapping(modelID: number)
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

#### Example:

```
const expressIdMapping = IfcAPI.CreateIfcGuidToExpressIdMapping(modelID);
```

Creates a map between element ExpressIDs and GlobalIDs. Each element has two entries, (ExpressID -> GlobalID) and (GlobalID -> ExpressID).

### CloseModel

```
IfcAPI.CloseModel(modelID: number)
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`, model must not be closed

#### Example:

```
IfcAPI.CloseModel(modelID);
```

Closes a model and frees all related memory

### IsModelOpen

```
IfcAPI.IsModelOpen(modelID: number): boolean
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

#### Example:

```
IfcAPI.IsModelOpen(modelID);
```

Checks if a specific model ID is open or closed

### LoadAllGeometry

```
IfcAPI.LoadAllGeometry(modelID: number): Vector
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

#### Example:

```
IfcAPI.LoadAllGeometry(modelID);
```

Load geometry for a single element

### SetGeometryTransformation

```
IfcAPI.SetGeometryTransformation(modelID: number,
                                  transformationMatrix: Array)
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

* `transformationMatrix` : Use `transformationMatrix` to encode transformations.

#### Example:

```
IfcAPI.SetGeometryTransformation(modelID, transformationMatrix);
```

 Configure the transformation of a geometry using `modelID` and `transformationMatrix`

### StreamAllMeshes

```
IfcAPI.StreamAllMeshes(modelID: number,
                      meshCallback:(mesh: FlatMesh))
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

* `meshCallback`: Use `mesh`.

#### Example:

```
IfcAPI.StreamAllMeshes(modelID, (mesh) => {});
```

Collect all `meshes` by `modelID` and `messCallback`

### StreamAllMeshesWithTypes

```
IfcAPI.StreamAllMeshesWithTypes(modelID: number, types: Array<number>,
                            meshCallback:(mesh: FlatMesh))
```

#### Arguments:

* modelID: Model handle retrieved by `OpenModel`, model must not be closed

* `types` : Select `type` of the `Array`

* `meshCallback`: Use `mesh`.

#### Example:

```
IfcAPI.StreamAllMeshesWithTypes(modelID, types, meshCallback);
```

Collect all `meshes` by `modelID` and `messCallback` with `type`.

### WriteLine

```
IfcAPI.WriteLine(modelID: number, lineObject: any)
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

* `lineObject`: Selected `lineObject` in a model.

#### Example:

```
IfcAPI.WriteLine(modelID, lineObject);
```

Write a line using `modelID` and `lineObject`

### WriteRawLineData

```
IfcAPI.WriteRawLineData(modelID: number, data: RawLineData)
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

* `data` : The raw `data` of each line

#### Example:

```
IfcAPI.WriteRawLineData(modelID);
```

Write a line data using `modelID` and `data`

## Get

### GetAllLines

```
IfcAPI.GetAllLines(modelID: Number): Vector
```

#### Arguments:

* `modelID`: Express ID of model

#### Example:

```
IfcAPI.GetAllLines(modelID);
```

Get all the lines of a model by its modelID

### GetAndClearErrors

```
IfcAPI.GetAndClearErrors(modelID: number): Vector
```

#### Arguments:

`modelID`: Express ID of model

#### Example:

```
return IfcAPI.GetAndClearErrors(modelID);
```

Get and clear errors using `modelID`

### GetCoordinationMatrix

```
IfcAPI.GetCoordinationMatrix(modelID: number): Array
```

#### Arguments:

* `modelID`: Express ID of model

#### Example:

```
IfcAPI.GetCoordinationMatrix(modelID);
```

Get the coordinate of a matrix using `modelID`

### GetFlatMesh

```
IfcAPI.GetFlatMesh(modelID: number, expressID: number): FlatMesh
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

* `expressID`: `expressID` of model.

#### Example:

```
IfcAPI.GetFlatMesh(modelID, expressID);
```

Load geometry for a single element

### GetGeometry

```
IfcAPI.GetGeometry(modelID: number, geometryExpressID: number): IfcGeometry
```

#### Arguments:

* `modelID`: `expressID` of ifcModel

* `geometryExpressID`: `expressID` of geometry in ifcModel.

#### Example:

```
const geometry = IfcAPI.GetGeometry(modelID, geometryExpressID);
```

Get `mesh` geometry using a `modelID`.

### GetIndexArray

```
IfcAPI.GetIndexArray(ptr: number, size: number): Uint32Array
```

#### Arguments:

* `ptr`: Parameter of get.
* `size`: Set `size`

#### Example:

```
IfcAPI.GetIndexArray();
```

Get `index` of `Array` using `ptr` and `size`.

### GetLine

```
IfcAPI.GetLine(modelID: number, expressID; number,
                flatten: boolean)
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

* `expressID`: `expressID` of model.

* `flatten`: Set whether it is `flatten` or not.

#### Example:

```
const props = IfcAPI.GetLine(modelID, id, (flatten = false));
```

Get the line using the modelID and expressID

### GetLineIdsWithType

```
IfcAPI.GetLineIdsWithType(modelId: number, type: number): Vector
```

#### Arguments:

* `modelID`: `expressID` of ifcModel

* `type`: Set of get `type`

#### Example:

```
const lines = IfcAPI.GetLineIDsWithType(modelID, type);
```

Defines the type to get

### GetRawLineData#

```
IfcAPI.GetRawLineData(modelID: number, expressID: number): RawLineData
```

#### Arguments:

* `modelID`: Model handle retrieved by `OpenModel`.

* `expressID`: `expressID` of model.

#### Example:

```
const rawLineData = IfcAPI.GetRawLineData(modelID, expressID);
```

Get a line of raw data using 'modelID' `and` 'expressID'

### getSubArray

```
IfcAPI.getSubArray(heap: any, startPtr: any,
                    sizeBytes: any)
```

#### Arguments:

* `heap`: Set to `stack`

* `startPtr`: Set to `startPtr` in `subArray`

* `sizeBytes`: Set to `sizeBytes`

#### Example:

```
const subArray = IfcAPI.getSubArray(heap, startPtr, sizeBytes);
```

Get a `subArray` in `Array`

### GetVertexArray

```
IfcAPI.GetVertexArray(ptr: number, size: number): Float32Array
```

#### Arguments:

* `ptr`: Set parameter of get.

* `size`: Set to `size`.

#### Example:

```
const vertexArray = IfcAPI.GetVertexArray(ptr, size);
```

Get the `vertex` of `Array`

---

# web-ifc-three

## Introduction

...but it has geometry.

[Web-ifc](https://ifcjs.github.io/info/docs/Guide/web-ifc-three/%22https://ifcjs.github.io/info/docs/Guide/web-ifc/Introduction%22) is a very powerful tool capable of reading and writing IFCs with near-native speed. However, almost all BIM applications show the user a 3D view of the models they are working with. You could use `web-ifc` in any graphics engine, but we have already done that for you in **web-ifc-three**.

`web-ifc-three` is a wrapper around `web-ifc` that reads all data from IFC files and transforms it into geometry that can be displayed and edited in any browser. You can install it with `npm i web-ifc-three` or `yarn add web-ifc-three`. Some cool facts about this module:

* It's super easy to use.

* It's the [official IFCLoader of Three.js](https://threejs.org/examples/webgl_loader_ifc.html).

* It's very efficient, being able to display thousands of objects at 60 fps in a browser. It can display multiple models, change materials and filter items.

* It can get and traverse the spatial structure tree of multiple files. Also, it can access the properties of all the items, both clicking on them in the 3d view and with smart filters.

In the following points, the API and its functionalities will be shown step by step. However, there are a couple of issues that are important to be clear about before using web-ifc-three.

### Can I use `web-ifc` directly?

With web-ifc you could build almost any BIM tool capable of reading and writing IFC. So why create a layer on top of it?

Because almost all BIM tools are 3D, and we think it would not make sense for all developers to implement a viewer from scratch. If you are only interested in the data, you may be better off using web-ifc directly.

In addition, web-ifc-three makes working with IFCs much easier and safer even for the developer who has no previous experience with the format.

* Web-ifc is way more flexible but requires more knowledge of the IFC schema and a greater implementation effort.

### Can I use the `THREE.IFCLoader` directly?

As mentioned above, `web-ifc-three` is the official IFCLoader of Three.js. That is, if you import the IFCLoader from Three.js, the code will be the same as the code you will find in the `web-ifc-three` repository.

You might be tempted to import the `IFCLoader` from Three.js to avoid importing `web-ifc-three` in your project. This should work, but beware that Three.js is a very large library, and its update rate is much slower than that of IFC.js.

* Slight delay: Three.js IFCLoader may not have the latest updates and the latest bugs we have fixed will remain unresolved in Three.js until the next version is released.

To use the `THREE.IFCLoader` instead of the original `IFCLoader` you only have to change the import statement:

```
// Import web-ifc-three (original) IFCLoader
import { IFCLoader } from "web-ifc-three/IFCLoader";

// Import three.js IFCLoader
import { IFCLoader } from "three/examples/jsm/loaders/IFCLoader";
```

## Setup

### DRY documentation

We don't want to [repeat ourselves](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself); not even in our documentation.

The setup for starting a project with web-ifc has already been seen in [Hello World](https://ifcjs.github.io/info/docs/Hello%20world). If you have skipped that point, we recommend you to go and have a look at it. All tutorials will start from that scene.

* You are free to follow these tutorials using the Three.js IFCLoader instead.

If you get lost in any of the tutorials, don't worry! Take a look at the examples [here](https://github.com/IFCjs/hello-world) or come to the [Discord channel](https://discord.gg/g7Uzn2KSwB) and ask us directly. Also, let us know of any suggestions so we can improve these docs.

* Before going forward: Basic knowledge of Three.js and web development is assumed. If you don't have this background, we recommend that you start [here](https://threejs.org/manual/) before jumping into IFC.js.

## API

All APIs are documented, so when you use any of the objects or methods seen in this documentation, you should see help in Intellisense, regardless of the IDE you are using. [Check it out!](https://github.com/IFCjs/web-ifc-three/blob/main/web-ifc-three/src/IFC/components/IFCManager.ts)

However, we realise that reading intellisense or comments is not the most comfortable thing to do, so on this page we will make an overview of what the API can do. Everything will be covered in more detail in specific tutorials later on.

### IfcLoader

The only object we will import from the library. It contains all the logic needed to work with IFC. You can use its `load()` and `loadAsync()` methods to load IFCs from a URL, [just like any other Three.js Loader](https://threejs.org/docs/#api/en/loaders/Loader.load). For example, to load an IFC we can do the following:

```
import { IFCLoader } from "web-ifc-three/IFCLoader";

const ifcLoader = new IFCLoader();
ifcLoader.load("models/Example_model.ifc", (ifcModel) => scene.add(ifcModel));
```

With `web-ifc-three` you can load multiple models in the scene. Many of the API operations are executed on a specified model. To express on which model we want to operate we have to give its `ModelID`.

You can get the ID of a model through the property `modelID`.

```
const modelID = ifcModel.modelID;
```

There are two ways to access the API:

* Through the instances of `IfcModel` that the `IfcLoader` generates with `load` and `loadAsync`.

* Through `IfcLoader.IfcManager`.

* Both **IfcModel** instances and **IfcLoader.IfcManager** can be used interchangeably to access the API. There's one difference: when using **IfcModel**, the ModelID never has to be given as an argument (it's known implicitly).

## Setup

### setWasmPath

```
async IfcLoader.IfcManager.setWasmPath (
                        path: string
                        ): void;
```

Specifies the location of the `web-ifc.wasm` and `web-ifc-mt.wasm` files. These files are the web-ifc file and is required to create any application with IFC.js. You can find them in `node_modules/web-ifc/`.

* Careful with your tooling!: If you use frameworks or libraries like React, Angular, Vue or Svelte it is possible that the root path of the project doesn't correspond to the root path of the served application. You will have to check in [each case](https://github.com/IFCjs/examples) how the paths of the statically served files are managed.

#### Arguments:

* `path` Route of `web-ifc.wasm`.

#### Example:

If `web-ifc.wasm` is in dist/wasmDir:

```
await ifcLoader.ifcManager.setWasmPath("dist/wasmDir/");
```

### setupThreeMeshBVH

```
IfcLoader.IfcManager.setupThreeMeshBVH (
                        computeBoundsTree: any,
                        disposeBoundsTree: any,
                        acceleratedRaycast: any
                        ): void;
```

This method allows object picking to be much faster, especially for very large models with heavy geometry. This method actually allows IFC.js to use the Garrett Johnson's amazing [library](https://github.com/gkjohnson/three-mesh-bvh) . u can install it with `npm i three-mesh-bvh` or `yarn add three-mesh-bvh`.

* Using this method not mandatory, but if you want to be able to select objects in medium / large IFC models at 60 fps, it's necessary.

#### Arguments:

* `computeBoundsTree` Pre-made BufferGeometry extension function that builds a new BVH, assigns it to boundsTree, and applies the new index buffer to the geometry. - [source](https://github.com/gkjohnson/three-mesh-bvh#computeboundstree).

* `disposeBoundsTree` BufferGeometry extension function that disposes of the BVH. - [source](https://github.com/gkjohnson/three-mesh-bvh#disposeboundstree).

* `acceleratedRaycast` Accelerated raycast function with the same signature as THREE.Mesh.raycast. Uses the BVH for raycasting if it's available otherwise it falls back to the built-in approach. - [source](https://github.com/gkjohnson/three-mesh-bvh#acceleratedraycast).

#### Example:

```
import { IFCLoader } from "web-ifc-three/dist/IFCLoader";

import { acceleratedRaycast, computeBoundsTree, disposeBoundsTree } from "three-mesh-bvh";

const ifcLoader = new IFCLoader();
ifcLoader.ifcManager.setupThreeMeshBVH(acceleratedRaycast, computeBoundsTree, disposeBoundsTree);
```

### setOnProgress

```
IfcLoader.IfcManager.setOnProgress (
      onProgress: (event: ParserProgress) => void
                                    ): void;
```

Sets a callback function that is called every 10% of IFC loaded. This way, you can display a loading bar to show your user how the loading is going.

#### Arguments:

* `onProgress`: Callback function that is called every 10%. That function must have one argument that that receives an object with two properties: `loaded` (number of objects loaded) and `total` (number of objects in the file).

#### Example:

```
function exampleCallback(event) {
  const progress = (event.total / event.progress) * 100;
  console.log("Progress: ", progress, "%");
}

ifcLoader.ifcManager.setOnProgress(exampleCallback);
```

### applyWebIfcConfig

```
async IfcLoader.IfcManager.applyWebIfcConfig (
                                    settings: LoaderSettings
                                    ): void;
```

Applies a configuration for [web-ifc](https://ifcjs.github.io/info/docs/Guide/web-ifc/Introduction), which is the parser that this library uses internally.

#### Arguments:

* `settings`: An object containing the following fields:

* `COORDINATE_TO_ORIGIN: boolean`: Wether to bring the model to the center of the scene. Useful for geolocated models.

* `USE_FAST_BOOLS: boolean`: Wether to use a faster (and less precise) boolean logic.

* `BOOL_ABORT_THRESHOLD?: number`: The limit to the boolean operation computation.

* `CIRCLE_SEGMENTS_LOW?: number`: The resolution for low segments curves.

* `CIRCLE_SEGMENTS_MEDIUM?: number`: The resolution for medium segments curves (e.g. IfcSweptDiskSolid).

* `CIRCLE_SEGMENTS_HIGH?: number`: The resolution for high segments curves (e.g. IfcCircle).

#### Example:

If a file is geolocated and we want to bring it to the origin of the scene:

```
await ifcLoader.ifcManager.applyWebIfcConfig({
  COORDINATE_TO_ORIGIN: true,
  USE_FAST_BOOLS: false,
});
```

### useWebworkers

```
async IfcLoader.IfcManager.useWebWorkers (
                                    active: boolean,
                                    path?: string
                                    ): void;
```

Toggles the web worker that contains the parsing logic. The rest of the API remains the same, but all the logic will happen in another thread of the machine, so the app will never be blocked by heavy operations.

You need to copy the file `IFCWorker.js` to your project and pass the relative path as a second argument.

#### Arguments:

* `active`: Wether to use web workers or not.

* `path`: Relative path to the worker file. Necessary if `active = true`.

#### Example:

If the file `IFCWorker.js` is in a folder called: `files`:

```
await ifcLoader.ifcManager.useWebWorkers({
                                true,
                                "files/IFCWorker.js"
                                            });
```

### useJSONData

```
async IfcLoader.IfcManager.useJSONData (
                                    useJSON: boolean
                                    ): void;
```

Uses JSON property data instead of the WASM data, which consumes much less memory. Only use this in the following scenarios:

* If you don't need to access the properties of the IFC

* If you will provide the properties as JSON. You can get the JSON from an IFC file in advance following [this example](https://github.com/IFCjs/hello-world/tree/main/examples/web-ifc/ifc-to-json/node).

#### Arguments:

* `useJSON`: Wether to use JSON data or not.

#### Example:

```
await ifcLoader.ifcManager.useJSONData(true);
```

### addModelJSONData#

```
async IfcLoader.IfcManager.addModelJSONData (
                                modelID: number,
                                data: { [id: number]: JSONObject
                                        ): void;
```

Adds the properties of a model as JSON data. If you are using web workers, use `loadJsonDataFromWorker()` instead to avoid overheads.

#### Arguments:

* `modelID`: ID of the IFC model.

* `data`: data as an object where the keys are the expressIDs and the values the properties. In addition, each value has the properties `expressID` (id of the item) and `type` (IFC class of the item).

#### Example:

```
await ifcLoader.ifcManager.addModelJSONData(0, jsonData);
```

### loadJsonDataFromWorker

```
async IfcLoader.IfcManager.loadJsonDataFromWorker (
                                        modelID: number,
                                        path: string
                                            ): void;
```

Loads the data of an IFC model from a JSON file directly from a web worker. If you are not using web workers, use `addModelJSONData()` instead.

#### Arguments:

* `modelID`: ID of the IFC model.

* `path`: the path to the JSON file **relative to the web worker file**.

#### Example:

```
await ifcLoader.ifcManager.loadJsonDataFromWorker(0, "path/to/data.json");
```

## Getters

### getExpressId

```
IfcLoader.IfcManager.getExpressId (
                        geometry: BufferGeometry,
                        faceIndex: number
                        ): number;
```

Gets the Express ID of an IFC element from a face index.

* Why a face index?: Because when we select an object in 3d space with the mouse we get the index of that face. We usually want the ID of the object where that face belongs to in order to highlight it, isolate it or get all its properties.

#### Arguments:

* `geometry` [Geometry](https://threejs.org/docs/#api/en/core/BufferGeometry) of the model you clicked on with the mouse.

* `faceIndex` Index of the face intersected with the [raycaster](https://threejs.org/docs/#api/en/core/Raycaster). If you are not familiar with the raycaster, don't worry; we'll cover this in detail in the tutorial about picking.

#### Example:

```
const intersected = raycaster.intersectObject(mesh)[0];
const index = intersected.faceIndex;
const id = ifcLoader.ifcManager.getExpressId(mesh, index);
```

### getIfcType

```
IfcLoader.IfcManager.getIfcType (
                        modelID: number,
                        id: number,
                        ): string;
```

Gets the IFC type of the specified element (e.g. IFCWALL).

* Elements in IFC always have an associated type: IfcWall, IfcSlab, IfcWindow, IfcDoor, etc.

#### Arguments:

* `modelID` ID of the IFC model.

* `id` Express ID of the item whose properties to obtain. You can get this either with `getExpressId` (if you are picking an object in the 3d view) or traversing the model with `getAllItemsOfType` or `getSpatialStructure`.

#### Example:

```
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const type = manager.getIfcType(model, id);
```

### getAllItemsOfType

```
async IfcLoader.IfcManager.getAllItemsOfType (
                            modelID: number,
                            type: number,
                            verbose: boolean
                            ): number[] | object[];
```

Returns all objects of the specified IFC type (e.g. all walls, all floors, all windows, etc.) of a specific model. It can return an array of `expressIDs`, or (if `verbose = true`) an array of objects containing the properties of the items found.

#### Arguments:

* `modelID` ID of the IFC model.

* `type` IFC type of the elements you want to get. You can import these types directly from `web-ifc` (see example below).

* `verbose` If true, gets the properties of all the items found. Be careful, as this can be a slow operation in bigger models.

#### Example:

```
import { IFCWALLSTANDARDCASE as W } from "web-ifc";

const manager = loader.ifcLoader.ifcManager;
const walls = await manager.getAllItemsOfType(0, W, false);
```

### getItemProperties

```
async IfcLoader.IfcManager.getItemProperties (
                            modelID: number,
                            id: number,
                            recursive = false
                            ): object[];
```

Gets the native properties of the given element. In the IFC schema there are two types of properties: direct and indirect. How to obtain the indirect properties (psets, qsets and type properties) will be discussed later.

* All methods related to properties return an array of objects where the keys are the name of the properties and the values are their values.

#### Arguments:

* `modelID` ID of the IFC model.

* `id` Express ID of the item whose properties to obtain. You can get this either with `getExpressId` (if you are picking an object in the 3d view) or traversing the model with `getAllItemsOfType` or `getSpatialStructure`.

* `recursive` If true, gets the properties of all the referenced elements recursively. Be careful, as this can be a slow operation in bigger models.

#### Example:

```
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const props = await manager.getItemProperties(model, id, false);
```

### getTypeProperties

```
async IfcLoader.IfcManager.getTypeProperties (
                            modelID: number,
                            id: number,
                            recursive = false
                            ): number[] | object[];
```

Gets the type properties of the given element.

#### Arguments:

* `modelID` ID of the IFC model.

* `id` Express ID of the item whose properties to obtain. You can get this either with `getExpressId` (if you are picking an object in the 3d view) or traversing the model with `getAllItemsOfType` or `getSpatialStructure`.

* `recursive` If true, gets the properties of all the referenced elements recursively. Be careful, as this can be a slow operation in bigger models.

#### Example:

```
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const props = await manager.getTypeProperties(model, id, false);
```

### getPropertySets

```
async IfcLoader.IfcManager.getPropertySets (
                            modelID: number,
                            id: number,
                            recursive = false
                            ): object[];
```

Gets the property sets and quantity sets of the given element.

* Property sets?: Native and type properties are those that are predefined by the IFC schema: they always contain the same information. Property sets, on the other hand, are arbitrary and can be defined by the user.

#### Arguments:

* `modelID` ID of the IFC model.

* `id` Express ID of the item whose properties to obtain. You can get this either with `getExpressId` (if you are picking an object in the 3d view) or traversing the model with `getAllItemsOfType` or `getSpatialStructure`.

* `recursive` If true, gets the properties of all the referenced elements recursively. Be careful, as this can be a slow operation in bigger models.

#### Example:

```
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const props = await manager.getPropertySets(model, id, false);
```

### getMaterialsProperties

```
async IfcLoader.IfcManager.getMaterialsProperties (
                            modelID: number,
                            id: number,
                            recursive = false
                            ): object[];
```

Gets the material information of the given element.

#### Arguments:

* `modelID` ID of the IFC model.

* `id` Express ID of the item whose properties to obtain. You can get this either with `getExpressId` (if you are picking an object in the 3d view) or traversing the model with `getAllItemsOfType` or `getSpatialStructure`.

* `recursive` If true, gets the properties of all the referenced elements recursively. Be careful, as this can be a slow operation in bigger models.

#### Example:

```
const model = ifcModel.modelID;
const id = 2142;
const manager = loader.ifcLoader.ifcManager;
const props = await manager.getMaterialsProperties(model, id, false);
```

### getSpatialStructure

```
async IfcLoader.IfcManager.getSpatialStructure (
                        modelID: number
                        ): object;
```

Gets the spatial structure of the project.

* The [spatial structure](https://standards.buildingsmart.org/IFC/DEV/IFC4_2/FINAL/HTML/schema/ifcproductextension/lexical/ifcspatialstructureelement.htm) is the hierarchical structure that organizes every IFC project (all physical items are referenced to an element of the spatial structure).

#### Arguments:

* `modelID` ID of the IFC model.

#### Example:

```
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
const ifcProject = await manager.getSpatialStructure(model);
```

## Subsets

### getSubset

```
IfcLoader.IfcManager.getSubset (
                        modelID: number,
                        material?: Material,
                        customID?: string
                        ): object;
```

Gets the mesh of the subset with the specified [material](https://threejs.org/docs/#api/en/materials/Material). If no material is given, this returns the subset with the original materials.

* Geometric subsets are extracts of the geometry of the model. For example, you could extract a subset with all the IfcDoors and IfcWindows that meet a certain condition and highlight or export them.

#### Arguments:

* `modelID` ID of the IFC model.

* `material` (optional) Material assigned to the subset (if any).

* `customID` (optional) Optional custom name of the subset (if any).

#### Example:

```
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
const subset = manager.getSubset(model);
```

### createSubset

```
IfcLoader.IfcManager.createSubset (
                        config: SubsetConfig
                        ): object;
```

Creates a new geometric subset.

#### Arguments:

* `config` A configuration object with the following options:

- `scene` Scene where the model is located.

- `modelID` ID of the model.

- `ids` Express IDs of the items of the model that will conform the subset.

- `removePrevious` Wether to remove the previous subset of this model with this material.

- `material` (optional) Material to apply to the subset. If no material is given, the subset has the original material.

- `customID` (optional) Optional custom name to give to the subset. This allows to create multiple subsets with the same material.

#### Example:

```
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

```
IfcLoader.IfcManager.removeSubset (
                        modelID: number,
                        material?: Material,
                        customID?: string,
                        ): object;
```

Removes the specified geometric subset.

#### Arguments:

* `modelID` ID of the IFC model.

* `material` (optional) Material assigned to the subset (if any).

* `customID` (optional) Optional custom name to give to the subset. This allows to create multiple subsets with the same material.

#### Example:

```
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
manager.removeSubset(model);
```

### removeFromSubset

```
IfcLoader.IfcManager.removeFromSubset (
                        modelID: number,
                        ids: number[],
                        customID?: string,
                        material?: Material
                        ): void;
```

Removes the specified items from the specified geometric subset.

#### Arguments:

* `modelID` ID of the IFC model.

* `ids` Express IDs of the items to remove from the subset.

* `customID` (optional) Optional custom name to give to the subset. This allows to create multiple subsets with the same material.

* `material` (optional) Material assigned to the subset (if any).

#### Example:

```
import { IFCWALLSTANDARDCASE as W } from "web-ifc";
const model = ifcModel.modelID;
const manager = loader.ifcLoader.ifcManager;
const walls = await manager.getAllItemsOfType(0, W, false);
manager.removeFromSubset(model, walls);
```

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
