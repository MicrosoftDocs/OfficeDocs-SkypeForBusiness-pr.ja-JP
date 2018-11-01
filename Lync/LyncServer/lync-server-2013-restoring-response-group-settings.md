---
title: 応答グループの設定の復元
TOCTitle: 応答グループの設定の復元
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Hh202174(v=OCS.15)
ms:contentKeyID: 52056594
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 応答グループの設定の復元

 

_**トピックの最終更新日:** 2013-02-18_

応答グループ アプリケーションを展開済みで、バック エンド サーバーまたは Standard Edition サーバーを復元する必要がある場合は、応答グループ構成設定も復元する必要があります。

## 応答グループ構成設定を復元するには

1.  コマンドラインで、次のように入力します。
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    例:
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

