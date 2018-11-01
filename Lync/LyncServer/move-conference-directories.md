---
title: 会議ディレクトリを移動する
TOCTitle: 会議ディレクトリを移動する
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48272441
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議ディレクトリを移動する

 

_**トピックの最終更新日:** 2012-10-04_

プールを使用停止にする前に、Office Communications Server 2007 R2 プール内の会議ディレクトリごとに以下の手順を実行する必要があります。

## 会議ディレクトリを Lync Server 2013 に移動するには

1.  Lync Server 管理シェルを開きます。

2.  組織の会議ディレクトリの ID を取得するには、次のコマンドを実行します。
    
        Get-CsConferenceDirectory
    
    このコマンドレットでは、組織のすべての会議ディレクトリが返されるので、使用停止にするプールのみに結果を絞り込んだ方がよい場合があります。たとえば、pool01.contoso.net という完全修飾ドメイン名 (FQDN) のプールを使用停止にする場合は、次のコマンドを実行します。
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    このコマンドレットでは、サービス ID に pool01.contoso.net という FQDN が含まれるすべての会議ディレクトリが返されます。

3.  会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    次に例を示します。
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

> [!NOTE]
> Active Directory からの更新されたアクセス許可セットを必要とする Lync Server 管理シェルが原因で、次のようなエラーが発生することがあります。エラーを解決するには、現在のウィンドウを閉じ、新しい Lync Server 管理シェルを開いてコマンドを再実行します。


![Move-CsConferenceDirectory のエラー出力](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory のエラー出力")

