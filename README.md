# vanila-test-task

## Решение первого задания находится по ссылке - <a href='https://vanila-test-task-ibeo.vercel.app/'>Первое задание</a>

## 2. Декодированная строка - .4-2.4-1.4-6.1-4.2-4.1-12.1-4.2-12.1-2.1-4.2-18.1-4.4-1.4-2.18-1.6-1.4-4.4-1.8-1.4-4.6-1.16-1.4-4.12-1.4-8.1-4.4-16.1-18.1-4.4-18.1-10.1-4.6-6.1-4.2-1.4-6.6-1.20-1.8-6.1-4.1-8.6-1.14

Код с решением второй задачи находится в файле ```main.js```

```javascript
const decode = code => code
  .replace(/-\d+|.\d+/g, x => ` ${x}`)
  .split(' ')
  .slice(1)
  .flatMap(x => {
    if (parseInt(x.slice(1)) !== 1) {
      return (parseInt(x.slice(1)) - 2) / 2
    } else {
      return '.'
    }
  })
  .join('')
  .match(/\d+.\d+/g)
  .map(e => e.split('.').reverse().map(e => parseInt(e)))
  .sort((a, b) => a[0] - b[0])
  .flatMap(e => String.fromCharCode(e.slice(1)))
  .join('')
```
