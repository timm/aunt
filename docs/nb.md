```awk
function List(i)      { split("",i,"") }
function Object(i)    { List(i); i["ois"] = "Object"; i["old"] = GOLD["oid"]++ } 
function isa(i,f1,f2) { @f2(i); GOLD["ois"][f1] = i["ois"]; i["ois"] = f1 }
function has(i,k,f)   { i[k][0]; delete i[k][0]; f ?  @f(i[k]) : List(i[k]) }
function have(i,f)    { k = length(i) + 1; has(i, k, f); return k }

function Emp(i) {
   isa(i,"Emp","Object")
   has(i,"prefs")
}
```
