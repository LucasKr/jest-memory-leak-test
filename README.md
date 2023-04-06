Run the following in your terminal:

```#bash!

dir=$(pwd)
i=1
while [ $i -le 1000 ]; do
  echo "${$(cat $dir/memoryLeakTests/__tests__/arquivosample.test.js)//TEST_NUMBER/$i}" > $dir/memoryLeakTests/__tests__/arquivo$i.test.js
  i=$(($i+1))
done
```

Run tests checking the memory

```
yarn test --logHeapUsage --no-color 2>jest.output.text
```
