go test -run none -bench . -benchtime 3s -benchmem -memprofile mem.out

// goes into pprof interactive mode
go tool pprof -alloc_space memcpu.test mem.out

list algoOne // look at method


go test -run none -bench . -benchtime 3s -benchmem -cpuprofile cpu.out
go tool pprof memcpu.test cpu.out
web // look at call graph
list algoOne

go build -gcflags "-m -m"
go build -gcflags "-m -l"


https://www.programmerall.com/article/46901728740/

https://github.com/DataDog/go-profiler-notes/blob/main/guide/README.md

https://golang.design/research/zero-alloc-call-sched/

## General Guideline on methods
- try not to return pointers
- Remove pointers within pointers
- when defining struct, define fields using less memory on top first
