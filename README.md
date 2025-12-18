$root = "C:\work"          # 検索ルート
$pattern = "ERROR"         # 探したい文字列（必要なら変更）

Get-ChildItem $root -Recurse -File -Filter *.java |
  Where-Object { $_.Name -notlike "*Test*" } |
  Select-String -Pattern $pattern -SimpleMatch -List |
  Select-Object -ExpandProperty Path
