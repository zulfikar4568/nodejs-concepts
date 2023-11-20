## Running the app
```bash
yarn start:dev
```

## Blocking
- In terminal 1
  ```bash
  curl -X GET http://localhost:3000/blocking
  ```
  See the CPU%, if you using mac just type `top`

- In terminal 2
  ```bash
  curl -X GET http://localhost:3000/
  ```
You will get `Hello World!` will appear after blocking finished. We will get blocking latency 10s.

## Non Blocking
- In terminal 1
  ```bash
  curl -X GET http://localhost:3000/nonBlocking
  ```
  See the CPU%, if you using mac just type `top`

- In terminal 2
  ```bash
  curl -X GET http://localhost:3000/
  ```
We will get the promises latency 10s. We will be able get `Hello World!` immediately.

## Concurrency
We will simulate using promises and parallel promises
### Promises
- In terminal 1
  ```bash
  curl -X GET http://localhost:3000/promises
  ```

- In terminal 2
  ```bash
  curl -X GET http://localhost:3000/
  ```
We will get the promises latency 10s. We will be able get `Hello World!` immediately. And output log
```js
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:17:51 PM     LOG Sleep complete
```

### Parallel Promises
- In terminal 1
  ```bash
  curl -X GET http://localhost:3000/promisesParallel
  ```

- In terminal 2
  ```bash
  curl -X GET http://localhost:3000/
  ```
We will get the parallel promises only latency 1s. We will be able get `Hello World!` immediately. And output log

```js
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:39 PM     LOG Start sleep
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
[Nest] 14133  - 11/17/2023, 3:27:40 PM     LOG Sleep complete
```