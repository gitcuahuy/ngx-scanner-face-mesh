# ngx-scanner-face-mesh

This library is built to provide a solution for detecting and marking human faces.\
This library analyzes each face and provides statistics for Angular web applications easily.\
Demo on the [stackblitz](https://stackblitz.com/edit/angular-ngx-scanner-face-mesh) or [github](https://id1945.github.io/ngx-scanner-face-mesh/).

![Logo](https://raw.githubusercontent.com/id1945/ngx-scanner-face-mesh/master/ngx-scanner-face-mesh.png)

## Installation
Install `ngx-scanner-face-mesh` from `npm`:
```bash
npm install ngx-scanner-face-mesh --save
```

Add wanted package to NgModule imports:
```typescript
import { NgxScannerFaceMeshModule } from 'ngx-scanner-face-mesh';
@NgModule({
    imports: [
        NgxScannerFaceMeshModule,
    ]
})
```

In the Component:

```html
<ngx-scanner-face-mesh #action="scanner" [isAuto]="true"></ngx-scanner-face-mesh>
<span>{{ action.data | async | json }}</span>
```

### API Documentation

#### Input

| Field         | Description       | Type                      | Default                                                                                 |
| ---           | ---               | ---                       | ---                                                                                     |
| [isAuto]      | auto load         | boolean                   | true                                                                                    |
| [src]         | image url         | string                    | -                                                                                       |
| [mesh]        | options           | Options                   | -                                                                                       |
| [config]      | config all        | BaseConfig                | -                                                                                       |
| [style]       | style for canvas  | UnknownObject             | `{width:'100%',height:'100%'}`                                   |
| [frame]       | style for canvas  | CanvasRenderingContext2D  | `{color:'#0BF6F4',lineWidth:.5}`                                                        |
| [medias]      | media config      | MediaStreamConstraints    | `{audio:false,video:{width:{ideal:1280},height:{ideal:720},facingMode:'environment'}}`  |

#### Ouput

| Field     | Description | Type      | Default |
| ---       | ---         | ---       | ---     |
| (event)   | data        | any       | -       |
| (error)   | error       | any       | -       |

#### Component export

| Field       | Description             | Type            | Default       |
| ---         | ---                     | ---             | ---           |
| isLoading   | status                  | boolean         | false         |
| isStart     | status                  | boolean         | true          |
| isPause     | status                  | boolean         | false         |
| data        | data                    | BehaviorSubject | -             |
| ---         | ---                     | ---             | ---           |
| (start)     | start camera            | AsyncSubject    | -             |
| (stop)      | stop camera             | AsyncSubject    | -             |
| (download)  | download with file name | AsyncSubject    | -             |

#### Models

<details><summary><b>BaseConfig</b></summary>

```typescript
interface BaseConfig {
  src?: string;
  isAuto?: boolean;
  isLoading?: boolean;
  mesh?: Options;
  frame?: UnknownObject;
  style?: UnknownObject;
  medias?: UnknownObject | MediaStreamConstraints;
};
```
</details>

<details><summary><b>UnknownObject</b></summary>

```typescript
interface UnknownObject {
  [key: string]: any;
}
```
</details>

#### Support versions
  
<table>
  <tr>
    <th colspan="2">Support versions</th>
  </tr>
  <tr>
    <td>Angular 14</td>
    <td>1.0.0</td>
  </tr>
</table>

#### Author Information
  
<table>
  <tr>
    <th colspan="2">Author Information</th>
  </tr>
  <tr>
    <td>Author</td>
    <td>DaiDH</td>
  </tr>
  <tr>
    <td>Phone</td>
    <td>+84845882882</td>
  </tr>
</table>

![Vietnam](https://raw.githubusercontent.com/id1945/ngx-scanner-face-mesh/master/vietnam.gif)

[MIT License](https://github.com/id1945/ngx-scanner-face-mesh/blob/master/LICENSE). Copyright (c) 2021 DaiDH