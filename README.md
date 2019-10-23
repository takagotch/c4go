### c4go
---
https://github.com/Konstantin8105/c4go

```go
// main_test.go

type programOut struct {
  stdout bytes.Buffer
  stderr bytes.Buffer
  isZero bool
}

var (
  buildFolder = "testdata"
  separator = string(os.PathSeparator)
)

func TestIntegrationScripts(t *testing.T) {
  testFile, err := filepath.Glob("tests/" + "*.c")
  if err != nil {
    t.Fatal(err)
  }
  
  testCppFiles, err := filepath.Glob("tests/" + "*.cpp")
  if err != nil {
    t.Fatal(err)
  }
  
  files := append(testFile, testCppFiles...)

  var (
    stdin = "7"
    args = []string{"some", "args"}
  )
  
  for _, file := range files {
    if strings.Contains(file, "debug.") {
      continue
    }
    t.Run(file, func(t *testing.T) {
      
      _ = os.Remove("debug.txt")
      defer func() {
      
      }()
      
      subFolder := buildFolder + separator + strings.Split(file, ".")[0] + separator
      
      err = os.MkdirAll(subFolder, os.ModulePerm)
      if err != nil {
        t.Fatalf("error: %v", err)
      }
      
      progs := []func() {
      }
      
      
    })
  }
}

```

```
```

```
```


