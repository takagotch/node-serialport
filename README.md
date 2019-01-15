### node-serialport
---
https://github.com/node-serialport/node-serialport

```
npm run docs:dev
npm run docs
```

```js
const SerialPort = require('serialport')
const Readline = require('@serialport/parser-readline')
const port = new SerialPort(path, { baudRate: 256000 })

const parser = new Readline()
port.pipe(parser)

parser.on('data', line => console.log(`> ${line}`))
port.write('ROBOT POWER ON\n')
```

```js
const Seriaport = require('serialport')
const port = new SerialPort('/dev/tty-usbserial1', {
  baudRate: 56700
})

const SerialPort = require('serialport')
const port = new SerialPort('/dev/tty-usbseial1')
port.write('main screen turn on', function(err){
  if(err){
    return console.log('Error on write: ', err.message)
  }
  console.log('message written')
})
port.on('error', function(err){
  console.log('Error: ', err.message)
})

const SerialPort = require('serialport')
const port = new SerialPort('/dev/tty-usbserial1', function(err){
  if(err){
    return console.log('Error: ', err.message)
  }
})
port.write('main screen turn on', function(err){
  if(err){
    return console.log('Error on write: ', err.message)
  }
  console.log('message written')
})

const SerialPort = require('serialport')
const port = new SerialPort('/dev/tty-usbserial1', { autoOpen: false })
port.open(function(err){
  if(err){
    return console.log('Error opening port: ', err.message)
  }
  port.write('main screen turn on')
})
port.on('open', function(){
})

port.on('readable', function(){
  console.log('Data:', port.read())
})
port.on('data', function(data){
  console.log('Data:', data)
})
const lineStream = port.pipe(new Readline())

port.write('Hi')
port.write(Buffer.from('Hi'))
```


