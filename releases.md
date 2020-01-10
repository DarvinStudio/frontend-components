# Changelog 

## [0.0.7] - 2020-01-10
### Changed
- в requestAnimationFrameComponent.add() добавлена возможность вторым необязательным аргементом передавать контекст для колбэка
- в requestAnimationFrameComponent.add() в колбэк передается deltaTime (время с последнего вызова requestAnimationFrame)

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

