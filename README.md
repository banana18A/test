(Get-ChildItem "C:\path\to\folder" -File -Recurse -Filter *.java).Count


$target = "ここに検索したい文字列"

Get-ChildItem -Directory | ForEach-Object {
    # そのフォルダ配下を再帰的に検索
    $count = (Get-ChildItem -Path $_.FullName -Recurse -File | Select-String -Pattern $target -List).Count
    
    # 結果をオブジェクトとして出力
    [PSCustomObject]@{
        フォルダ名 = $_.Name
        ヒット数   = $count
    }
} | Format-Table -AutoSize
