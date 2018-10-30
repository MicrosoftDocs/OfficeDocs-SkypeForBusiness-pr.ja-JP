---
title: 共有エリアの電話の連絡先オブジェクトを削除する
TOCTitle: 共有エリアの電話の連絡先オブジェクトを削除する
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994087(v=OCS.15)
ms:contentKeyID: 52056750
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 共有エリアの電話の連絡先オブジェクトを削除する

 

_**トピックの最終更新日:** 2013-02-20_

共有エリアの電話に関連付けられた連絡先オブジェクトを削除する必要が生じることがあります。たとえば、従業員休憩室から電話を撤去した場合、その電話に関連付けられている連絡先オブジェクトは不要になります。この場合は **Remove-CsCommonAreaPhone** コマンドレットを使用することで、共有エリアの電話アカウントを削除できます。このコマンドレットを実行すると、**Get-CsCommonAreaPhone** から戻される共有エリアの電話の一覧から電話が削除されます。さらに、この電話に関連付けられている連絡先オブジェクトは Active Directory ドメイン サービス から削除されます。

**Remove-CsCommonAreaPhone** を使用すると、1 つの共有エリアの電話または表示名、国コード、地域コードなど、共通の要素を持つすべての共有エリアの電話が削除されます。このコマンドレットは、Lync Server 2013 管理シェルからでも、Windows PowerShell のリモート セッションからでも実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。


## 指定された共有エリアの電話を削除する

  - 次のコマンドは SIP アドレスが sip:mainlobby@litwareinc.com である共有エリアの電話を削除します。
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

## 表示名に基づいて共有エリアの電話を削除する

  - このコマンドは表示名に文字列値 "Building 14" を含む共有エリアの電話をすべて削除します。
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

## 国コードと地域コードに基づいて共有エリアの電話を削除する

  - このコマンドは米国 (国コード 1) および地域コード 425 の共有エリアの電話をすべて削除します。
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

詳細については、[Remove-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCommonAreaPhone) コマンドレットに関するヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[Get-CsCommonAreaPhone](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCommonAreaPhone)

