$root = "C:\work"   # 親フォルダに変更

Get-ChildItem $root -Directory | ForEach-Object {
  $count = Get-ChildItem $_.FullName -File -Filter *.java -Recurse -ErrorAction SilentlyContinue |
           Where-Object { $_.Name -notlike "*Test*" } |
           Measure-Object | Select-Object -ExpandProperty Count

  [pscustomobject]@{
    Folder = $_.Name
    Count  = $count
  }
} | Format-Table -AutoSize

