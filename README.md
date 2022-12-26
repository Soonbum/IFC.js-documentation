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

Next, we'll create the rollup configuration file. This file has to be called `rollup.config.js` and includes the reference to the plugins we have previously installed.

* Rollup? Rollup is a very popular bundling library. For instance, it's the bundler used by Three.js. Take a look at the [rollup docs](https://rollupjs.org/guide/en/) to learn more.

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

Also, the `package.json` file needs to be modified to contain the commands to control rollup easily. In each command, you'll have to specify the relative path to your rollup configuration file. If we have installed everything correctly, we should see the same dependencies in this file (the version of the libraries may differ).

* `npm run build` will bundle the project and create a file called `bundle.js` in the root directory of the project.

* `npm run watch` will activate the `watch mode`, updating that file automatically every time we make changes to the code and save it.

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

The next thing to do is to copy the `web-ifc.wasm` and `web-ifc-mt.wasm` files to a directory in your project. It can be found in `node_modules\web-ifc` (or `node_modules\three\examples\jsm\loaders\ifc` if you are only using Three's IFCLoader). We can copy them wherever we want; in this example, they will be copied to a folder called wasm in the root directory of the project.

These files are necessary because they contain the compiled C++ logic of [web-ifc](https://github.com/IFCjs/web-ifc), which is the parsing core to read and write IFC files with native speed.

* These files have to be served statically in your application. This might need different tweaks if you are using frameworks or libraries like React, Angular, Vue or Svelte.

## Setting up a 3D scene

Finally, we are going to create the JavaScript file to write the code for our application. This file can be located anywhere and have any name, but you must reflect this in the `rollup.config.js`.

We are going to create a basic 3D scene using Three.js.

```
import { AmbientLight, AxesHelper, DirectionalLight, GridHelper, PerspectiveCamera, Scene, WebGLRenderer } from "three";
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls";

//Creates the Three.js scene
const scene = new Scene();

//Object to store the size of the viewport
const size = {
  width: window.innerWidth,
  height: window.innerHeight,
};

//Creates the camera (point of view of the user)
const aspect = size.width / size.height;
const camera = new PerspectiveCamera(75, aspect);
camera.position.z = 15;
camera.position.y = 13;
camera.position.x = 8;

//Creates the lights of the scene
const lightColor = 0xffffff;

const ambientLight = new AmbientLight(lightColor, 0.5);
scene.add(ambientLight);

const directionalLight = new DirectionalLight(lightColor, 1);
directionalLight.position.set(0, 10, 0);
directionalLight.target.position.set(-5, 0, 0);
scene.add(directionalLight);
scene.add(directionalLight.target);

//Sets up the renderer, fetching the canvas of the HTML
const threeCanvas = document.getElementById("three-canvas");
const renderer = new WebGLRenderer({
  canvas: threeCanvas,
  alpha: true,
});

renderer.setSize(size.width, size.height);
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

//Creates grids and axes in the scene
const grid = new GridHelper(50, 30);
scene.add(grid);

const axes = new AxesHelper();
axes.material.depthTest = false;
axes.renderOrder = 1;
scene.add(axes);

//Creates the orbit controls (to navigate the scene)
const controls = new OrbitControls(camera, threeCanvas);
controls.enableDamping = true;
controls.target.set(-2, 0, 0);

//Animation loop
const animate = () => {
  controls.update();
  renderer.render(scene, camera);
  requestAnimationFrame(animate);
};

animate();

//Adjust the viewport to the size of the browser
window.addEventListener("resize", () => {
  size.width = window.innerWidth;
  size.height = window.innerHeight;
  camera.aspect = size.width / size.height;
  camera.updateProjectionMatrix();
  renderer.setSize(size.width, size.height);
});
```

To run the application locally we will need a local server. If you are using VS Code as IDE, one option is to install the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer), which allows us to open an instance of Google Chrome, run our web application and see the changes we make to the code in real-time.

## Loading IFC files

### Loading user's models

Finally, we will use IFC.js to load IFC files. This can be done by instantiating the loader and creating an event for when the user uploads an IFC file to the HTML input element.

```
import { IFCLoader } from "web-ifc-three/IFCLoader";

// Sets up the IFC loading
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

Keep in mind that if you haven't saved the wasm files in the root of served files of the project, you'll need to specify its location with `setWasmPath`. For instance, if we had them stored in a folder called `wasm` contained in a folder called `static` in the root of the project, we would do the following:

```
ifcLoader.ifcManager.setWasmPath("static/wasm/");
```

If you have done everything correctly, you should be able to see something similar to [this](https://ifcjs.github.io/hello-world/examples/web-ifc-three/helloworld/) in your local server. From here, the possibilities are endless.

### Loading our models

In the previous point we saw how to load BIM models directly, and that's great. What if we want to show our BIM models instead of allowing the user to upload theirs? This is very simple. Generally there are two possibilities:

* Having the IFC in the same application where you want to display it.

* Having to get it from an external storage service.

In the first case, it is sufficient to reference the URL of the IFC file. That is, its relative path in the application. For example, if the IFC is in a folder called "models" in the root of the project, we could load that IFC when starting the application as follows:

```
ifcLoader.load("models/Example_model.ifc", (ifcModel) => scene.add(ifcModel));
```

* Getting a file from a remote storage service varies depending on the service used. However, the logic is the same: get the information, create a URL and pass it as an argument to the IFCLoader.

## Conclusion

Congratulations! You have just created your first IFC viewer. Go to the next pages of the docs to find out what else can you do with IFC.js.

* What else can I do with IFC.js? This is just the beginning. You can take a look at [web-ifc-viewer](https://github.com/IFCjs/web-ifc-viewer), which includes tools for object selection, changing geometry appearance, section planes and much more. You can try it [here](https://ifcjs.github.io/web-ifc-viewer/example/index).

---

# 시작하기

?

---

# 바운티 다루기

?

---

# web-ifc

?

---

# web-ifc-three

?

---

# web-ifc-viewer

?

> 출처: https://ifcjs.github.io/info/docs/Introduction/
