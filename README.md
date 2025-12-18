```
$root = "C:\work"   # ←親フォルダに変更

$rows = Get-ChildItem $root -Directory | ForEach-Object {
  $count = Get-ChildItem $_.FullName -File -Filter *.java -Recurse -ErrorAction SilentlyContinue |
           Where-Object { $_.Name -like "*Test*" } |
           Measure-Object | Select-Object -ExpandProperty Count

  [pscustomobject]@{
    Folder = $_.Name
    Count  = $count
  }
}

$rows | Format-Table -AutoSize
"TOTAL`t$($rows | Measure-Object Count -Sum | Select-Object -ExpandProperty Sum)"

```

