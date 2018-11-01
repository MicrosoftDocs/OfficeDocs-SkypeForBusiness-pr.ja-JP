---
title: 'Lync Server 2013: 会議参加ページの構成'
TOCTitle: 会議参加ページの構成
ms:assetid: 45880423-47f4-49af-b825-cbd8e3fc1046
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204861(v=OCS.15)
ms:contentKeyID: 48271953
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での会議参加ページの構成

 

_**トピックの最終更新日:** 2015-03-09_

ユーザーがミーティング出席依頼のミーティング リンクをクリックすると、ミーティング参加ページが、ユーザーのコンピューターに Lync 2013 クライアントが既にインストールされているかどうかを検出します。クライアントが既にインストールされている場合、クライアントがミーティングを開き、参加します。クライアントがインストールされていない場合、既定では 2013 バージョンの Lync Web App が開きます。

ユーザーが Office Communicator 2007 R2 または Lync 2010 Attendant を使用してミーティングに参加できるようにする場合は、ミーティング参加ページの動作を変更できます。これらの設定オプションは Lync Server 2013 コントロール パネルから削除されましたが、Set-CsWebServiceConfiguration コマンドレットを使用して設定できます。

### ミーティング参加ページの Set-CsWebServiceConfiguration パラメーター

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Set-CsWebServiceConfiguration パラメーター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ShowJoinUsingLegacyClientLink</p></td>
<td><p>True に設定した場合、Lync 以外のクライアント アプリケーションを使用してミーティングに参加するユーザーに、Office Communicator 2007 R2 を使用してミーティングに参加する機会が提供されます。既定値は False です。</p></td>
</tr>
<tr class="even">
<td><p>ShowAlternateJoinOptionsExpanded</p></td>
<td><p>True に設定されている場合、オンライン会議に参加するための別のオプション (Office Communicator 2007 R2 など) が自動的に展開され、ユーザーに表示されます。False (既定値) に設定されている場合、これらのオプションは使用できますが、ユーザーが自分でオプションの一覧を表示する必要があります。</p></td>
</tr>
</tbody>
</table>


## Lync Server 2013 管理シェルを使用して会議参加ページを構成するには

1.  Lync Server 2013 管理シェルを次の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Web サービス構成設定を表示するには、次のコマンドレットを実行します。
    
        Get-CsWebServiceConfiguration

3.  パラメーターを適宜 True または False に設定して、次のコマンドを実行します (このコマンドレットのパラメーターの詳細については、Lync Server 2013 管理シェルのドキュメントの「[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)」を参照してください)。
    
        Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True

## 関連項目

#### その他のリソース

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration)

