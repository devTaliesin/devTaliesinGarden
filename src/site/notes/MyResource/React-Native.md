---
{"dg-publish":true,"permalink":"/my-resource/react-native/","dgPassFrontmatter":true}
---

# What is React-Natice
## 페이스북이 개발한 오픈 소스 모바일 애플리케이션 프레임워크
- 리액트 컴포넌트를 사용하여 iOS 및 Android용 네이티브 앱을 개발
- [[Swift\|Swift]] 또는 [[Kotlin\|Kotlin]]으로 개발된 네이티브 앱과 동일한 성능을 제공

# How To Use React-Native

## React Native CLI
[[MyResource/Node.js\|Node.js]]
[[jdk\|jdk]]
[[MyResource/Android Studio\|Android Studio]]

npm uninstall -g react-native-cli @react-native-community/cli
[[npx\|npx]] react-native@latest init MyApp 
npm start
npm run android
## Expo CLI

# React-Native Grammar
## component
## Props
## State
- 변경 가능한 모든 데이터
``` TypeScript
[var, setVar] = useState('init'); 
```
## DisPatch
- 상태 업데이트 합수
```TypeScript
dispatch({email : '', password: ''})
```
## Hook
- Componet에서 State, 생존주기, 부가효과 등을 관리할 수 있는 도구
>[!note] Kind of Hook
>useState : 상태 관리
>useEffent : 부가효과 관리
>useContext : Context API 사용
>useReducer : Reducer 관리
>useMemo : 값 Caching
>useCallback : 콜백 함수 Caching
>useRef : 참조 관리
## Type - (TypeScript)
### JSX.Element
JSX문법을 사용할 때 반환되는 요소의 타입
React 요소 생성
가상 DOM으로 랜더링 시점에서  실제 DOM으로 변환

### PropWithChideren
``` tsx
PropsWithChildren<{title: string;}>;
```
 React 컴포넌트가 자식 요소를 포함하도록 정의된 경우, 이러한 요소를 다루기 위해 주로 사용

### React.FC<'type of props'>
Function Componet를 나타내는 타입 
``` tsx
const Section: React.FC<PropsWithChildren<{title: string;}>> = ({children, title}) => {}
```

# React-Navigator

## What is React-Navigator

## Dependency
### react-native-reanimated
- Drawer Navigator 사용에 필요한 종송성
### react-native-gesture-handler
- Stack Navigator 사용에 필요한 종속성
- Drawer Navigator 사용에 필요한 종송성
### react-native-screens
### react-native-safe-area-context
### @react-native-community/masked-view
## React-Navigator Library
### @react-navigation/native  
- 네비게이션 사용에 필수
- import { NavigationContainer } from '@react-navigation/native';
- NavigationContainer 컴포넌트로 감싸진 자식 컴포넌트에서 네비게이션이 동작
### @react-navigation/stack  
#### init :
1. Create RootParamList Type
```ts
export type RootParamList = {
 FirstScreen: undefined;
...
}
```
2. Create Stack Navigator
``` ts
const StackNavigator = createStackNavigator<RootStackParamList>();
```
3. Create Navigation Container
```ts
    <SafeAreaProvider>
      <NavigationContainer>
        <StackNavigator.Navigator
          initialRouteName="AuthMain"
          screenOptions={NavigationOpt}>
          <StackNavigator.Screen 
	          name="FirstScreen" 
	          component={FirstScreen} />
	      ...
        </Stack.Navigator>
      </NavigationContainer>
    </SafeAreaProvider>
```
4. Create Screen Props
```ts
./firstScreen
export type FirstScreenProps = StackScreenProps<RootParamList, 'FirstScreen'>;
export const FirstScreenProps = ({navigation, route}: FirstScreenProps): JSX.Element => {...}
```
5. Create Navigator Funtion
```ts
const onPressEvent = (name: keyof RootStackParamList) => {
    navigation.navigate(name)
  }
```
### @react-navigation/drawer  

### @react-navigation/bottom-tabs  
### @react-navigation/material-top-tabs
## Kind of React-Navigator
### Stack Navigator
### Tab Navigator
### Drawer Navigator

## How To Use React-Navigator
- NavigationContainer - 최상위 컴포넌트, 내비게이션의 최상위에 위치해야 한다.
- Navigator는 여러 개의 Screen 컴포넌트를 자식으로 가진다.
- Navigator의 자식으로는 Screen 컴포넌트만 와야 한다.
- Screen 컴포넌트는 name, component 속성을 가지고, name이 스크린의 이름, component는 연결할 화면 컴포넌트를 지정한다.
- Screen은 props로 항상 navigation과 route를 가진다.
- Props.navigation.navigate(“컴포넌트 name”, 건네줄 state 객체); 로 화면을 이동할 수 있다.
- Props.navigation.navigate.goBack() 메서드로 뒤로 이동할 수 있다.  
- 스크린에 다른 네비게이션 컴포넌트를 연결하여 중첩해서 네비게이션을 구현할 수 있다.
# HTTP Method

## Fetch API
- Base Module
## Axios

### How To Use Axios
 - npm install axios
### .get
```typeScript
const get = (command: String) => {
	axios
		.get(`${url}/command`)
		.then(res => {
			if (res === ){
				/ 동작
			}
		})
		.catch(error => {
			if (error === ) {
				/ 동작
			} else {
				/ 동작
			}
		})
}
```
### .post
```typeScript
const post = (command: String, a:String, b:String) => {
	axios
		.post(`${url}/command`, {
			a: a,b: b
			})
		.then(res => {
			if (res === ){
				/ 동작
			}
		})
		.catch(error => {
			if (error === ) {
				/ 동작
			} else {
				/ 동작
			}
		})
}
```
### res.data
### error.respose.status
# Dimentsions
## UseDimensions
- Dimensions.get();
## Set Dimentions
- Dimensions.set();
# StyleSheet.Create
# TouchableOpacity

# State Management

## Context APt
```TypeScript
import { createContext, useContext, useReducer } from 'react';
```
### Context
- 
```TypeScript
const TasksContext = createContext(null); 
const TasksDispatchContext = createContext(null); /동작 context
```
### Reducer
-
```TypeScript
const tasksReducer = (tasks, action) => {
  switch (action.type) {
    case 'added': {
      return [...tasks, {
        id: action.id,
        text: action.text,
        done: false
      }];
    }
    case 'changed': {
      return tasks.map(t => {
        if (t.id === action.task.id) {
          return action.task;
        } else {
          return t;
        }
      });
    }
    case 'deleted': {
      return tasks.filter(t => t.id !== action.id);
    }
    default: {
      throw Error('Unknown action: ' + action.type);
    }
  }
}

export function TasksProvider({ children }) {
  const [tasks, dispatch] = useReducer(
    tasksReducer,
    initialTasks
  );

  return (
    <TasksDispatchContext.Provider value={dispatch}>
	    <TasksContext.Provider value={tasks}>
      
        {children}
      
	    </TasksContext.Provider>
    </TasksDispatchContext.Provider>
  );
}
```
### Recap
- Reducer를 Context와 결합하면 모든 구성 요소가 부모 구성요소에 있는 State를 읽고 업데이트할 수 있습니다.

- 자식 Component에 State, Dispath Function을 전달하는 방법.
    1. State와 Dispatch Functions를 위한 두 개의 Contexts 생성.
    2. Reducer를 사용하는 Component로 부터 두 Context 전달.
    3. 이걸을 전달받을 컴포넌트에서 두 Context를 사용

- 모든 연결을 하나의 파일로 옮겨 component들을 깔끔하게 정리할 수 있다. 
    - `TasksProvider` 가 Context를 전달하는 것 처럼 component를 export할 수 있다.
    - 또한 Context를 읽기 위한 `useTasks`와 `useTasksDispatch`같은 custom Hooks를 export할 수 있다.
## Redux
## Redux Toolkit

# Status Bar Size
```bash
npm install --save react-native-status-bar-height

```

```jsx
import { getStatusBarHeight } from 'react-native-status-bar-height';
import { StatusBar, Platform } from 'react-native';

const StatusBarHeight =
    Platform.OS === 'ios' ? getStatusBarHeight(true) : StatusBar.currentHeight;

const headerStyle: {
	backgroundColor: 'red',
	height: 50 + StatusBarHeight,
},
```

# KeyboardAvoidingView
## KeyboardVerticalOffset
### Android
 - Default Value(0) = Window Height - StatusBar Height 만큼 올라간다.
 - StatusBar Height = Window Height만큼 화면이 올라간다. Keyboard에 가려지던 모든 Component가 표시된다.
 - StatusBar Height - Bottom Component Height = Bottom Component의 Heighy만큼 덜 올라간다. Bottom Component를 제외한 Component가 표시된다.
## behavior
### Android
- "heght" 높이를 조절하는 방식으로 동작한다

## Truble
### 키보드 생성, 제거 후 초기화 되지 않는 문제 
# TochableWithoutFeedback
## 하나의 자식 Component

# View For Stack views
## position: 'relative'
- position: 'absolute' styleProp를 가진 하위 객체의 기준 객체
## position: 'absolute'
- position: 'relative' styleProp를 가진 상위 객체 기준의 위치를 조정을 활성화

# TextInput 
## Props
 - blurOnSubmit
 - onChangeText
 - placeholder
 - onSubmitEditing
 - secureTextEntry