# helpJS ⭐️

These are some utils for javascript developer Yay!


```bash
const help = {}

## ARRAY

help.difference = (a, b) => {
    const s = new Set(b);
    return a.filter(x => !s.has(x));
};
help.similar = (a, b) => {
    const s = new Set(b);
    return a.filter(x => s.has(x));
};
help.differenceBy = (a, b, fn) => {
    const s = new Set(b.map(fn));
    return a.filter(x => !s.has(fn(x)));
};
help.similarBy = (a, b, fn) => {
    const s = new Set(b.map(fn));
    return a.filter(x => s.has(fn(x)));
};
help.byteSize = str => new Blob([str]).size;
help.removeFalsy = arr => arr.filter(Boolean);
help.returnOnly = (arr, fn) => arr.filter(fn);
help.all = (arr, fn = Boolean) => arr.every(fn);
help.findLast = (arr, fn) => arr.filter(fn).pop();
help.findFirst = (arr, fn) => arr.filter(fn).shift();
help.allEqual = arr => arr.every(val => val === arr[0]);
help.provedLenghth = (arr, fn) => arr.filter(fn).length;
help.fromLeft = (arr, count = 1) => arr.slice(0, count);
help.sum = (...nums) => nums.reduce((acc, val) => acc + val, 0);
help.average = (...nums) => nums.reduce((acc, val) => acc + val, 0) / nums.length;
help.approximatelyEqual = (v1, v2, epsilon = 0.001) => Math.abs(v1 - v2) < epsilon;
help.filterNonUnique = arr => arr.filter(i => arr.indexOf(i) === arr.lastIndexOf(i));
help.countOccurrences = (arr, val) => arr.reduce((a, v) => (v === val ? a + 1 : a), 0);
help.fromRight = (arr, n = 1) => arr.slice(n > arr.length ? 0 : arr.length - n, arr.length)
help.deepFlatten = arr => [].concat(...arr.map(v => (Array.isArray(v) ? deepFlatten(v) : v)));
help.occurrencesIndex = (arr, val) => arr.reduce((a, v, i) => (v === val ? a.push(i) : a, a), []);
help.arrayToCSV = (arr, delimiter = ',') => arr.map(v => v.map(x => `"${x}"`).join(delimiter)).join('\n');
help.bifurcateBy = (arr, fn) => arr.reduce((acc, val, i) => (acc[fn(val, i) ? 0 : 1].push(val), acc), [[], []]);
help.bifurcate = (arr, filter) => arr.reduce((acc, val, i) => (acc[filter[i] ? 0 : 1].push(val), acc), [[], []]);
help.averageBy = (arr, fn) =>
    arr.map(typeof fn === 'function' ? fn : val => val[fn]).reduce((acc, val) => acc + val, 0) / arr.length;

## STRING

help.reverseString = str => [...str].reverse().join('');
help.capitalize = (str) =>
    str.split(' ').map(([first, ...rest]) => first.toUpperCase() + rest.join('')).join(' ');

## HTML

help.bottomVisible = () => document.documentElement.clientHeight + window.scrollY >=
    (document.documentElement.scrollHeight || document.documentElement.clientHeight);

## URL

help.currentURL = () => window.location.href;
help.currentORIGIN = () => window.location.origin;
help.currentPATH = () => window.location.pathname;
help.currentHOST = () => window.location.hostname;
help.currentHOST = () => window.location.hostname;
help.currentPROTOCOL = () => window.location.protocol;

## DATE

const timeEnum = {
    sec: 1000,
    min: 60 * 1000,
    hour: 60 * 60 * 1000,
}

help.fromToday = (days) => {
    let t = new Date();
    t.setDate(t.getDate() + days);
    return t.toISOString().split('T')[0];
};
help.isAfterDate = (dateA, dateB) => dateA > dateB;
help.getTime = date => date.toTimeString().slice(0, 8);
help.maxDate = (...dates) => new Date(Math.max.apply(null, ...dates));
help.minDate = (...dates) => new Date(Math.min.apply(null, ...dates));
help.isSameDate = (dateA, dateB) => dateA.toISOString() === dateB.toISOString();
help.dateDifferenceBy = (dateA, dateB, factor) => (dateA - dateB) / timeEnum[factor];
help.passedDayOfYear = date => Math.floor((date - new Date(date.getFullYear(), 0, 0)) / 1000 / 60 / 60 / 24);
help.getDaysDiffBetweenDates = 
    (dateInitial = new Date(), dateFinal = new Date()) => Math.floor((dateFinal - dateInitial) / (1000 * 3600 * 24));

## MATH

help.degreesToRads = deg => (deg * Math.PI) / 180.0;
help.radsToDegrees= deg => (deg  * 180.0) / Math.PI;
help.digitize = n => n.toString().split('').map(a => parseInt(a))
help.distance = ([x0, y0], [x1, y1]) => Math.hypot(x1 - x0, y1 - y0);

## JS

help.isValidJSON = str => {
    try {
      JSON.parse(str);
      return true;
    } catch (e) {
      return false;
    }
};
help.functionName = fn => fn.name
help.isObject = obj => obj === Object(obj);
help.isNumber = val => typeof val === 'number';
help.isNil = val => val === undefined || val === null;
help.is = (type, val) => ![, null].includes(val) && val.constructor === type;
help.getType = v => v === undefined ? 'undefined' : v === null ? 'null' : v.constructor.name.toLowerCase();

module.exports = help

```


## Thanks
 You guys can copy paste those function that You need for your work no need to install heavy library. Star ⭐️my repo if it helps you.

## License
[MIT](https://choosealicense.com/licenses/mit/)
