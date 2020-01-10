# Darvin Studio frontend components
[download via npm](https://www.npmjs.com/package/@darvins/frontend)

## Changelog 

### [0.0.7] - 10.01.2020
### requestAnimationFrameComponent
- добавлена возможность вторым необязательным аргементом передавать контекст для колбэка
- в колбэк передается deltaTime (время с последнего вызова requestAnimationFrame)

Пример
```js
import requestAnimationFrameComponent from '@darvins/frontend/utils/request-animation-frame';

export default class Test {
    constructor(container, element){
        this.text = 'deltaTime: '
        // this.update - callback
        // this - контекст (экземпляр класса Test)
        requestAnimationFrameComponent.add(this.update, this);
    }

    update(deltTime) {
        // deltTime прошедшее время в мс
        console.log(this.text + deltTime);
        // do something useful... 
    }
}
```

