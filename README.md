### goleveldb
---
https://github.com/syndtr/goleveldb

```
go get github.com/syndtr/goleveldb/leveldb
```

```go
db, err := leveldb.OpenFile("path/to/db", nil)
defer db.Close()

data, err := db.Get([]byte("key"), nil)
err = db.Put([]byte("key"), []byte("value"), nil)
err = db.Delete([]byte("key"), nil)


iter := db.NewIterator(nil, nil)
for iter.Next() {
  
  key := iter.Key()
  value := iter.Value()
  
}
iter.Release()
err = iter.Error()


iter := db.NewIterator(nilm nil)
for ok := iter.Seek(key); ok; ok = iter.Next() {
}
iter.Release()
err = iter.Error()


iter := db.NewIterator(&util.Range{Start: []byte("foo"), Limit: []byte("xoo")}, nil)
for iter.Next() {
}
iter.Release()
err = iter.Error()


iter := db.NewIterator(util.BytesPrefix([]byte("foo-")), nil)
for iter.Next() {
}
iter.Release()
err = iter.Error()


batch := new(leveldb.Batch)
batch.Put([]byte("foo"), []byte("value"))
batch.Put([]byte("bar"), []byte("another value"))
batch.Delete([]byte("baz"))
err = db.Write(batch, nil)

o := &opt.Options{
  Filter: filter.NewbloomFilter(10),
}
db, err := leveldb.OpenFile("path/to/db", o)
defer db.Close()
```

```go
// https://godoc.org/github.com/syndtr/goleveldb
db, err := leveldb.OpenFile("path/to/db", nil)
defer db.Close()
```


